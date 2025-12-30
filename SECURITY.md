# Security Policy

## 🔒 Security at ThreadMill Education

We take the security of ThreadMill Education seriously. We appreciate your efforts to responsibly disclose your findings and will make every effort to acknowledge your contributions.

## 📋 Supported Versions

We release patches for security vulnerabilities in the following versions:

| Version | Supported          |
| ------- | ------------------ |
| 0.1.x   | :white_check_mark: |
| < 0.1   | :x:                |

**Note**: As this is a new project, we currently support only the latest version. As the project matures, we will extend support to multiple versions.

## 🚨 Reporting a Vulnerability

**Please do not report security vulnerabilities through public GitHub issues.**

If you discover a security vulnerability, please follow these steps:

### 1. Report via Email

Send details to: **[security@threadmill.education]** or create a private security advisory on GitHub.

To create a private security advisory:
1. Go to the [Security tab](https://github.com/Aspect022/ThreadMill/security) of this repository
2. Click "Report a vulnerability"
3. Fill in the details of the vulnerability

### 2. Include in Your Report

Please include as much of the following information as possible:

- **Type of vulnerability** (e.g., XSS, SQL injection, authentication bypass)
- **Full paths of source file(s)** related to the vulnerability
- **Location of the affected source code** (tag/branch/commit or direct URL)
- **Step-by-step instructions** to reproduce the issue
- **Proof-of-concept or exploit code** (if possible)
- **Impact of the vulnerability**, including how an attacker might exploit it
- **Any potential mitigations** you've identified

### 3. What to Expect

- **Initial Response**: Within 48 hours of submission
- **Status Update**: Within 7 days with a more detailed response
- **Resolution Timeline**: We aim to resolve critical issues within 30 days

### 4. Disclosure Policy

- We will confirm receipt of your vulnerability report
- We will provide regular updates on our progress
- We will notify you when the vulnerability is fixed
- We will publicly acknowledge your responsible disclosure (unless you prefer to remain anonymous)

## 🎯 Scope

### In Scope

The following are within the scope of our security program:

- **Authentication vulnerabilities**
- **Authorization bypasses**
- **Cross-Site Scripting (XSS)**
- **Cross-Site Request Forgery (CSRF)**
- **Server-Side Request Forgery (SSRF)**
- **SQL Injection** (if applicable)
- **Remote Code Execution**
- **API security issues**
- **Sensitive data exposure**
- **Session management issues**
- **Cryptographic vulnerabilities**

### Out of Scope

The following are **not** in scope:

- **Social engineering attacks**
- **Physical attacks**
- **Denial of Service (DoS/DDoS)** attacks
- **Spam or social engineering via the platform**
- **Issues in third-party dependencies** (report these to the maintainers)
- **Issues requiring unlikely user interaction**
- **Reports from automated tools without validation**
- **Best practices without clear security impact**
- **Vulnerabilities in outdated browsers**
- **Missing security headers** without demonstrated impact

## 🛡️ Security Best Practices for Contributors

If you're contributing to ThreadMill, please follow these security practices:

### Environment Variables

```bash
# ✅ Good: Use environment variables for secrets
const apiKey = process.env.GOOGLE_GENERATIVE_AI_API_KEY

# ❌ Bad: Never commit secrets
const apiKey = "AIzaSyD..." // Don't do this!
```

### Input Validation

```typescript
// ✅ Good: Validate and sanitize user input
import { z } from "zod"

const schema = z.object({
  subject: z.string().min(1).max(100),
  level: z.enum(["Beginner", "Intermediate", "Advanced"])
})

const validated = schema.parse(userInput)

// ❌ Bad: Use raw user input
const subject = req.body.subject // Dangerous!
```

### API Security

```typescript
// ✅ Good: Validate on the server
"use server"
export async function generateLearningPath(subject: string, level: string) {
  // Server-side validation
  if (!subject || !level) {
    throw new Error("Invalid input")
  }
  // ... process
}

// ❌ Bad: Trust client-side data
export async function unsafeAction(data: any) {
  // No validation!
  return await database.query(data)
}
```

### Authentication

```typescript
// ✅ Good: Use secure authentication libraries
import { auth } from "@/lib/auth" // Trusted auth library

export async function protectedAction() {
  const session = await auth()
  if (!session) {
    throw new Error("Unauthorized")
  }
  // ... proceed
}

// ❌ Bad: Roll your own auth
function checkAuth(token: string) {
  return token === "secret123" // Insecure!
}
```

### Dependencies

```bash
# Regularly check for vulnerabilities
npm audit
pnpm audit

# Keep dependencies updated
pnpm update
```

## 🔐 Security Features in ThreadMill

### Current Security Measures

1. **Server Actions**: All AI interactions happen server-side via Next.js Server Actions
2. **Environment Variables**: API keys stored in environment variables, never committed
3. **Input Validation**: User inputs validated with Zod schemas
4. **Type Safety**: TypeScript for compile-time type checking
5. **CSP Headers**: Content Security Policy configured (if applicable)
6. **HTTPS**: Enforced in production deployments

### Planned Security Features

- [ ] User authentication with secure session management
- [ ] Rate limiting on API endpoints
- [ ] CSRF protection for forms
- [ ] XSS protection with proper sanitization
- [ ] SQL injection prevention (when database is added)
- [ ] Security headers (X-Frame-Options, X-Content-Type-Options, etc.)
- [ ] Regular security audits
- [ ] Dependency scanning automation

## 🏆 Security Acknowledgments

We believe in recognizing security researchers who help us keep ThreadMill safe. 

### Hall of Fame

Security researchers who responsibly disclose vulnerabilities will be acknowledged here (with their permission):

- *No vulnerabilities reported yet*

### Recognition Tiers

- **Critical**: Featured prominently + special acknowledgment
- **High**: Listed in Hall of Fame + mentioned in release notes
- **Medium**: Listed in Hall of Fame
- **Low**: Acknowledged in security page

## 📚 Resources

### Security Best Practices

- [OWASP Top Ten](https://owasp.org/www-project-top-ten/)
- [Next.js Security Best Practices](https://nextjs.org/docs/app/building-your-application/configuring/content-security-policy)
- [React Security Best Practices](https://react.dev/learn/escape-hatches#security-pitfalls)
- [Node.js Security Best Practices](https://nodejs.org/en/docs/guides/security/)

### Reporting Standards

- [Common Vulnerability Scoring System (CVSS)](https://www.first.org/cvss/)
- [CVE Numbering Authority](https://cve.mitre.org/)

## 📞 Contact

For security-related questions or concerns:

- **Email**: security@threadmill.education (if available)
- **GitHub Security Advisories**: [Report a vulnerability](https://github.com/Aspect022/ThreadMill/security/advisories/new)

For general support:
- **Issues**: [GitHub Issues](https://github.com/Aspect022/ThreadMill/issues)
- **Discussions**: [GitHub Discussions](https://github.com/Aspect022/ThreadMill/discussions)

## 📜 Policy Updates

This security policy may be updated from time to time. Major changes will be announced in:
- Project README
- Release notes
- Security advisories (if applicable)

**Last Updated**: December 30, 2025

---

**Thank you for helping keep ThreadMill Education and our users safe!** 🔒✨
