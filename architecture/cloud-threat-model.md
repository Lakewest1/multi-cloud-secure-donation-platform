# Threat Model (STRIDE)

## Spoofing
- Mitigated via Cloudflare Turnstile and token validation

## Tampering
- Server-side validation
- Immutable Lambda deployments

## Repudiation
- CloudWatch audit logs
- API Gateway access logs

## Information Disclosure
- TLS 1.2+ enforced
- CSP headers
- No PII stored

## Denial of Service
- Cloudflare rate limiting
- Lambda concurrency limits

## Elevation of Privilege
- IAM least privilege roles
- No wildcard permissions
