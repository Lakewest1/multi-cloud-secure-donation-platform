
---

## Security Controls Implemented

### 1. Software Composition Analysis (SCA)

**Tools Used:**
- `npm audit`
- `depcheck`
- **Snyk Open Source**

**Purpose:**
- Detect known vulnerabilities in third-party dependencies
- Identify unused or unnecessary packages that increase attack surface

**Execution Stage:** Pre-build

**Security Impact:**
- Prevents vulnerable libraries from reaching production
- Reduces supply-chain risk
- Minimizes dependency footprint

**Policy:**
- Builds blocked on high or critical vulnerabilities
- Vulnerable dependencies patched or replaced before merge

---

### 2. Static Application Security Testing (SAST)

**Tools & Methods:**
- ESLint with security-focused rules
- Snyk Code (where applicable)
- Manual secure code review

**Focus Areas:**
- Input validation
- Authentication logic
- Authorization enforcement
- Secure handling of secrets
- Injection and logic flaws

**Execution Stage:** Pre-build

**Security Impact:**
- Catches vulnerabilities early in development
- Enforces secure coding standards
- Reduces remediation cost

---

### 3. Build & Artifact Integrity

- Immutable build artifacts
- Deterministic builds
- No runtime code modification
- Secure environment variable injection

**Security Impact:**
- Prevents artifact tampering
- Ensures integrity from build to deployment

---

### 4. Manual Security Approval Gate

- Production deployments require explicit approval
- Security checklist validated before release
- Prevents unauthorized or accidental deployments

---

### 5. Secrets Management

- No secrets committed to source control
- No secrets stored in CI/CD configuration
- Secrets retrieved at runtime from **AWS Secrets Manager**

**Security Impact:**
- Eliminates credential leakage
- Supports secret rotation without redeployment

---

### 6. Deployment Strategy

- Serverless deployment (AWS Lambda)
- Versioned releases with rollback support
- Zero-downtime deployment model

---

### 7. Dynamic Application Security Testing (DAST)

**Methodology:**
- Manual attack simulation
- WAF rule validation at Cloudflare edge

**Attack Scenarios Tested:**
- SQL Injection attempts
- Cross-Site Scripting (XSS)
- Rate-limit bypass attempts
- Invalid CORS requests
- Automated bot traffic

**Execution Stage:** Post-deployment

**Outcome:**
- 100% of tested attacks blocked
- No successful exploitation observed
- Attacks mitigated within <1 second

---

## DevSecOps Alignment

| Principle | Implementation |
|--------|----------------|
| Shift-left security | SCA + SAST before build |
| Supply-chain security | Snyk + npm audit + depcheck |
| Defense in depth | CI security + WAF + runtime controls |
| Least privilege | Minimal IAM permissions |
| Secure by default | Insecure builds blocked |
| Observability | Logs and alerts post-deployment |

---

## Risk Reduction Summary

| Risk | Mitigation |
|----|------------|
| Vulnerable dependencies | Snyk, npm audit |
| Unused attack surface | depcheck |
| Insecure code | SAST + manual review |
| Secret exposure | Secrets Manager |
| Unauthorized deployments | Approval gate |
| Runtime exploitation | DAST + WAF |

---

## Compliance Support

This pipeline supports:
- **PCI DSS Req 6:** Secure development lifecycle
- **GDPR Art 25:** Data protection by design
- **Audit readiness:** Repeatable, documented controls

---

## Summary

This CI/CD pipeline demonstrates a **real-world DevSecOps implementation** integrating:
- Automated dependency and vulnerability scanning
- Static and dynamic security testing
- Secure secrets management
- Controlled production deployments

Security is embedded **from commit to production**, not added after release.
