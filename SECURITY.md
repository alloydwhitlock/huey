# Security Policy

## Supported Versions

| Version | Supported          |
| ------- | ------------------ |
| Latest  | :white_check_mark: |
| < Latest| :x:                |

## Reporting a Vulnerability

If you discover a security vulnerability in the Huey Hugo theme, please report it by:

1. **Do NOT** open a public GitHub issue
2. Email the maintainer 
3. Include:
   - Description of the vulnerability
   - Steps to reproduce
   - Potential impact
   - Suggested fix (if available)

You should receive a response within 48 hours. If the vulnerability is accepted, we will:

- Develop and test a fix
- Release a patched version
- Publicly disclose the vulnerability after users have time to update

## Security Best Practices for Users

When using the Huey theme:

1. Keep Hugo updated to the latest version (minimum 0.154.2)
2. Configure security headers on your hosting platform (see netlify.toml example)
3. Use HTTPS for all external resources
4. Review and customize the Content-Security-Policy for your needs
5. Regularly update the theme to the latest version

## Security Considerations

The Huey theme is designed for static site generation with Hugo, which provides inherent security benefits:

- No server-side code execution
- No database or backend vulnerabilities
- Content is generated at build time, not runtime
- Reduced attack surface compared to dynamic CMSs

However, proper configuration of security headers and HTTPS on your hosting platform is still essential for a secure deployment.
