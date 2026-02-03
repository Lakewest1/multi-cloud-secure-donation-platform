# Cloud Security Architecture

This platform uses a **serverless-first security architecture** with security controls enforced at multiple layers to minimize blast radius and reduce operational overhead.

## Components
- **Cloudflare Edge**
  - WAF (OWASP Top 10)
  - Bot Management
  - Rate Limiting
  - DDoS Mitigation
- **AWS API Gateway**
  - TLS 1.2+
  - Request throttling
  - Structured access logs
- **AWS Lambda**
  - IAM least privilege
  - Input validation
  - Token verification
- **AWS Secrets Manager**
  - Encrypted secrets
  - No hardcoded credentials
- **Monitoring**
  - CloudWatch Logs
  - Alarms + SNS notifications

## Design Principles
- Zero Trust
- Least Privilege
- Defense in Depth
- Cost-Aware Security
