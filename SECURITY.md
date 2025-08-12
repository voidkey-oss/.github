# Security Policy

## Reporting Security Vulnerabilities

We take the security of Voidkey seriously. If you believe you have found a security vulnerability in any Voidkey repository, please report it to us responsibly.

### Please DO NOT:
- Create a public GitHub issue for security vulnerabilities
- Disclose the vulnerability publicly until it has been addressed
- Test vulnerabilities against production systems

### Please DO:
- Email us directly at: **security@voidkey.com**
- Provide detailed information about the vulnerability
- Include steps to reproduce the issue if possible
- Allow us reasonable time to address the issue

## What to Include in Your Report

Please include as much of the following information as possible:

- **Component**: Which repository/component is affected (broker-core, broker-server, cli, sandbox)
- **Description**: A clear description of the vulnerability
- **Impact**: What the potential impact could be
- **Reproduction Steps**: Step-by-step instructions to reproduce the issue
- **Environment**: Relevant environment details (OS, versions, etc.)
- **Proof of Concept**: If applicable, include a minimal proof of concept

## Response Timeline

- **Initial Response**: We aim to acknowledge receipt within 48 hours
- **Investigation**: We will investigate and provide an initial assessment within 5 business days
- **Resolution**: We will work to resolve confirmed vulnerabilities as quickly as possible
- **Disclosure**: Once resolved, we will work with you on appropriate disclosure timing

## Security Best Practices for Voidkey

As a credential broker system, Voidkey handles sensitive authentication and authorization data. We follow these security principles:

### Core Security Features
- **Zero-Trust Architecture**: No long-lived credentials stored or shared
- **Token Validation**: All OIDC tokens validated against provider JWKS endpoints
- **Temporary Credentials**: Only short-lived, scoped credentials are minted
- **Secure Communication**: All API communications over HTTPS/TLS
- **Input Validation**: Comprehensive validation of all inputs and tokens

### Development Security Practices
- **Dependency Scanning**: Regular scanning of dependencies for vulnerabilities
- **Code Review**: All changes require review before merging
- **Automated Testing**: Security-focused testing in CI/CD pipelines
- **Secrets Management**: No secrets committed to repositories
- **Principle of Least Privilege**: Minimal permissions for all operations

### Deployment Recommendations
- **Network Security**: Deploy behind proper firewall and network controls
- **TLS/SSL**: Always use TLS for all communications
- **Environment Isolation**: Separate development, staging, and production environments
- **Monitoring**: Implement comprehensive logging and monitoring
- **Regular Updates**: Keep all dependencies and systems up to date

## Supported Versions

We provide security updates for the following versions:

| Component | Version | Supported |
| --------- | ------- | --------- |
| broker-core | Latest | ✅ |
| broker-server | Latest | ✅ |
| cli | Latest | ✅ |
| sandbox | Latest | ✅ |

## Security Considerations for Users

### Configuration Security
- **Identity Provider Configuration**: Ensure proper OIDC configuration and JWKS endpoints
- **Access Provider Credentials**: Use service accounts with minimal required permissions
- **Network Access**: Restrict network access to the broker server appropriately
- **Audit Logging**: Enable and monitor all audit logs

### Runtime Security
- **Token Handling**: Ensure OIDC tokens are handled securely by clients
- **Credential Lifecycle**: Use temporary credentials promptly and allow them to expire
- **Environment Variables**: Protect environment variables containing configuration
- **Regular Rotation**: Regularly rotate service account credentials

## Known Security Considerations

### By Design
- **Token Validation**: The broker validates incoming OIDC tokens but relies on proper IdP configuration
- **Provider Trust**: The system trusts configured identity and access providers
- **Network Security**: The broker server should be deployed with appropriate network controls
- **Audit Trails**: Consider implementing audit logging for credential minting operations

### Limitations
- **Client Security**: The security of client applications using Voidkey is the responsibility of the client
- **Provider Security**: Security of configured identity and access providers is outside Voidkey's control
- **Network Transport**: While Voidkey enforces HTTPS, network-level security is deployment-dependent

## Security Updates

When security vulnerabilities are resolved:

1. **Private Fix**: We develop and test the fix privately
2. **Security Advisory**: We publish a GitHub Security Advisory when appropriate
3. **Release**: We release updated versions with the fix
4. **Communication**: We notify the community through appropriate channels
5. **CVE Assignment**: We request CVE assignment for significant vulnerabilities

## Contact

For security-related questions or concerns:
- **Email**: security@voidkey.com
- **General Contact**: andrew@voidkey.com

## Recognition

We appreciate security researchers who help improve Voidkey's security. With your permission, we're happy to acknowledge your contribution in our security advisories and release notes.

---

Thank you for helping keep Voidkey secure! 🔒