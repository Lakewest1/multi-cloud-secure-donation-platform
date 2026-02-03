# Encryption Strategy

## Data in Transit
- TLS 1.2+ enforced (API Gateway)
- HTTPS only (Cloudflare)
- No HTTP fallback

## Data at Rest
- Environment variables encrypted by default (Lambda)
- Secrets Manager for production (planned upgrade)

## Key Management
- AWS ACM for TLS certificates
- Automatic rotation enabled


