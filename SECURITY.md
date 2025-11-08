# Security Policy

## Supported Versions

We release security updates for the following versions:

| Version | Supported          |
| ------- | ------------------ |
| 1.0.x   | :white_check_mark: |
| < 1.0   | :x:                |

---

## Reporting a Vulnerability

We take security vulnerabilities seriously. If you discover a security issue in LampStack, please follow these steps:

### 1. Do Not Publicly Disclose

Please **do not** open a public GitHub issue for security vulnerabilities. This helps protect users while we work on a fix.

### 2. Report Via Email

Send a detailed report to: **im.ashish.1001@gmail.com**

Include the following information:
- Description of the vulnerability
- Steps to reproduce the issue
- Potential impact and severity
- Suggested fix (if available)
- Your contact information

### 3. Response Timeline

- **Initial Response**: Within 48 hours
- **Status Update**: Within 5 business days
- **Fix Timeline**: Depends on severity
  - Critical: 7 days
  - High: 14 days
  - Medium: 30 days
  - Low: 60 days

### 4. Disclosure Policy

Once a fix is available:
1. We will notify you that the issue has been resolved
2. A security advisory will be published on GitHub
3. Credit will be given to the reporter (unless anonymity is requested)

---

## Security Best Practices

When deploying LampStack in production:

### Environment Variables

Never commit sensitive credentials:
```bash
# Bad - DO NOT DO THIS
MISTRAL_API_KEY=sk-1234567890abcdef

# Good - Use environment variables
MISTRAL_API_KEY=${MISTRAL_API_KEY}
```

### JWT Secrets

Use strong, randomly generated JWT secrets:
```bash
# Generate secure secret
openssl rand -base64 64
```

### Database Security

1. **PostgreSQL**:
   - Use strong passwords (16+ characters)
   - Enable SSL/TLS connections
   - Restrict network access (firewall rules)
   - Regular backups with encryption

2. **Milvus**:
   - Enable authentication in production
   - Use network isolation
   - Encrypt data at rest

### API Security

1. **Rate Limiting**: Implement rate limiting on all endpoints
2. **CORS**: Configure allowed origins (avoid `*` in production)
3. **HTTPS**: Always use TLS/SSL in production
4. **Input Validation**: Sanitize all user inputs
5. **Authentication**: Require JWT tokens for all protected endpoints

### Dependency Management

Keep dependencies updated:
```bash
# Java
./mvnw versions:display-dependency-updates

# Python
pip list --outdated

# Node.js
npm outdated
```

---

## Known Security Considerations

### 1. External API Keys

LampStack integrates with external services:
- **Mistral AI**: API key required for OCR
- **Google Places API**: API key for contact validation
- **NPI Registry**: Public API (no key required)

**Recommendation**: Use separate API keys per environment (dev/staging/prod) with appropriate usage limits.

### 2. Data Privacy

Healthcare provider data may include sensitive information:
- Store data encrypted at rest (PostgreSQL encryption)
- Use TLS for data in transit
- Implement access controls and audit logging
- Comply with HIPAA/GDPR regulations if applicable

### 3. File Uploads

CSV upload endpoint accepts user files:
- Validate file types (only `.csv`)
- Limit file size (max 10MB recommended)
- Scan for malicious content
- Use antivirus scanning in production

### 4. WebSocket Security

Real-time notifications via WebSockets:
- Authenticate WebSocket connections
- Validate message payloads
- Implement connection rate limiting

---

## Security Scanning

We recommend running security scans:

### Java (Spring Boot)
```bash
./mvnw org.owasp:dependency-check-maven:check
```

### Python
```bash
pip install safety
safety check
```

### Node.js
```bash
npm audit
```

### Docker
```bash
docker scan lampstack:latest
```

---

## Compliance

LampStack can be configured to comply with:
- **HIPAA**: Healthcare data protection (requires additional configuration)
- **GDPR**: Data privacy regulations
- **SOC 2**: Security controls framework

For compliance assistance, contact: im.ashish.1001@gmail.com

---

## Security Updates

Subscribe to security advisories:
- GitHub Security Advisories: [Watch Repository](https://github.com/CroWzblooD/LampStack)
- Email notifications: Enable in GitHub settings

---

## Acknowledgments

We appreciate responsible disclosure from security researchers. Contributors will be acknowledged in:
- GitHub Security Advisories
- Release notes
- This security policy (with permission)

---

**Last Updated**: November 8, 2025
