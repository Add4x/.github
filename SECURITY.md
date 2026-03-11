# Security Policy

## Reporting a Vulnerability

If you discover a security vulnerability in any Add4x repository, please report it responsibly.

**Do NOT open a public GitHub issue for security vulnerabilities.**

Instead, please email security concerns to the repository maintainers directly.

## Supported Versions

Only the latest release of each service is supported with security updates.

## Security Practices

- All services use Clerk for authentication
- Backend validates JWTs using JWKS
- Role-based access control (RBAC) with 5-tier hierarchy
- Environment secrets are never committed to repositories
- Dependencies are regularly audited and updated
