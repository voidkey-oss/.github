# Contributing to Voidkey

Thank you for your interest in contributing to Voidkey! We welcome contributions from the community and appreciate your help in making this project better.

## Getting Started

Voidkey is a zero-trust credential broker system consisting of multiple repositories:

- **[broker-core](https://github.com/voidkey-oss/broker-core)** - TypeScript core library
- **[broker-server](https://github.com/voidkey-oss/broker-server)** - NestJS HTTP server
- **[cli](https://github.com/voidkey-oss/cli)** - Go CLI client
- **[sandbox](https://github.com/voidkey-oss/sandbox)** - Docker development environment

## Ways to Contribute

- **Bug Reports**: Found a bug? Please create an issue with detailed reproduction steps
- **Feature Requests**: Have an idea? Open an issue to discuss it
- **Code Contributions**: Submit pull requests for bug fixes or new features
- **Documentation**: Help improve our docs, examples, or README files
- **Testing**: Help us test new features or edge cases

## Development Setup

### Prerequisites
- Node.js 18+ (for TypeScript components)
- Go 1.21+ (for CLI)
- Docker & Docker Compose (for sandbox)

### Quick Start
1. Clone the repository you want to work on
2. Follow the setup instructions in that repo's README
3. Make your changes
4. Test thoroughly
5. Submit a pull request

### Component-Specific Guidelines

#### broker-core & broker-server (TypeScript/Node.js)
```bash
npm install
npm run build
npm test
npm run test:coverage
```

#### cli (Go)
```bash
go mod download
go build -o voidkey main.go
go test ./...
go fmt ./...
```

#### sandbox (Docker)
```bash
docker-compose up -d
# Test your changes against the sandbox environment
```

## Pull Request Process

1. **Fork** the repository and create a feature branch from `main`
2. **Make your changes** following our coding standards
3. **Add tests** for new functionality
4. **Update documentation** if needed
5. **Run the full test suite** and ensure all tests pass
6. **Submit a pull request** with a clear description

### PR Requirements
- [ ] Tests pass locally
- [ ] Code follows existing style conventions
- [ ] Documentation updated if needed
- [ ] PR description explains the change and why it's needed
- [ ] Commits are well-formed and focused

## Coding Standards

### General Guidelines
- Write clear, self-documenting code
- Follow existing patterns and conventions in each repository
- Keep functions and classes focused and small
- Use meaningful variable and function names

### TypeScript (broker-core, broker-server)
- Follow existing ESLint and Prettier configurations
- Use TypeScript strict mode
- Prefer explicit types over `any`
- Write comprehensive Jest tests

### Go (cli)
- Follow Go conventions and `go fmt` formatting
- Use standard Go testing patterns
- Handle errors appropriately
- Write clear, idiomatic Go code

### Documentation
- Update README files for significant changes
- Add inline comments for complex logic
- Update API documentation for interface changes

## Testing

- All new code should have appropriate tests
- Maintain or improve test coverage
- Test both happy path and error conditions
- Include integration tests where applicable

### Running Tests
```bash
# TypeScript components
npm test
npm run test:coverage

# Go CLI
go test ./...
go test -race ./...

# End-to-end testing
cd sandbox && ./scripts/e2e-test.sh
```

## Issue Guidelines

### Bug Reports
- Use a clear, descriptive title
- Describe the expected vs actual behavior
- Include steps to reproduce
- Add relevant environment details
- Include logs or error messages

### Feature Requests
- Clearly describe the feature and its benefits
- Explain the use case and problem it solves
- Consider implementation complexity
- Be open to alternative solutions

## Security

For security vulnerabilities, please see our [Security Policy](SECURITY.md) instead of opening a public issue.

## Code of Conduct

This project follows our [Code of Conduct](CODE_OF_CONDUCT.md). Please review it before contributing.

## Questions?

- Check existing issues and discussions
- Review repository-specific documentation
- Contact us at: andrew@voidkey.com

## License

By contributing to Voidkey, you agree that your contributions will be licensed under the same license as the project.

---

Thank you for contributing to Voidkey! 🚀