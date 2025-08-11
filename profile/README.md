# Voidkey

Voidkey is a zero-trust credential broker system that provides secure, temporary credential minting for cloud resources through OIDC-based authentication.

## Overview

Voidkey enables organizations to implement zero-trust access patterns by brokering temporary credentials based on verified identity tokens. Instead of storing long-lived credentials, users authenticate with their identity provider and receive short-lived, scoped credentials for cloud resources.

## Repositories

- **[broker-core](https://github.com/voidkey-oss/broker-core)** - TypeScript core library containing credential minting logic
- **[broker-server](https://github.com/voidkey-oss/broker-server)** - NestJS HTTP server exposing the broker API
- **[cli](https://github.com/voidkey-oss/cli)** - Go CLI client for interacting with the broker
- **[sandbox](https://github.com/voidkey-oss/sandbox)** - Docker development environment with Keycloak and MinIO

## Key Features

- **OIDC Integration** - Works with Auth0, Okta, GitHub Actions, and other identity providers
- **Multi-Cloud Support** - Supports AWS, GCP, MinIO and other access providers
- **Key-Based Configuration** - Fine-grained access control with individual keys and provider configs
- **Real Credential Minting** - Generates actual temporary credentials via STS APIs
- **Zero-Trust Architecture** - No long-lived credentials stored or shared

## How It Works

1. Users authenticate with configured identity providers
2. OIDC tokens are validated against provider JWKS endpoints
3. Token subjects are mapped to configured keys with provider access
4. Temporary credentials are minted via cloud provider STS APIs
5. Short-lived credentials are returned to the client

## API Endpoints

- `POST /credentials/mint` - Mint credentials using configured keys
- `GET /credentials/keys` - List available keys for authenticated subject
- `GET /credentials/idp-providers` - List configured identity providers
- `GET /health` - Health check endpoint

## Development

The project uses TypeScript for core logic and server components, Go for the CLI client, and Docker for local development. Jest is used for testing across TypeScript components.

---

For questions or more information, contact: **andrew@voidkey.com**