# IAM Policy Strategy

## Principles
- Least privilege
- Service-specific roles
- No long-lived credentials

## Controls
- Lambda execution role restricted to:
  - CloudWatch Logs
  - Secrets Manager (specific ARNs only)
- No wildcard (`*`) permissions
- IAM policies reviewed quarterly

## Risk Reduction
- Prevents lateral movement
- Limits blast radius of compromised functions

## Lambda Execution Role

### Trust Policy
```json
{
  "Version": "2012-10-17",
  "Statement": [{
    "Effect": "Allow",
    "Principal": {"Service": "lambda.amazonaws.com"},
    "Action": "sts:AssumeRole"
  }]
}
```

### Permissions Policy
- ✅ CloudWatch Logs only
- ❌ NO S3 access
- ❌ NO EC2 access
- ❌ NO DynamoDB access

**Principle:** Least privilege - grant only what's needed.