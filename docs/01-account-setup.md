# Exercise 01 — AWS Account Setup and Security

**Date:** 2026-08-15 
**Status:** Completed

## What I Did

1. Enabled MFA on root account
2. Created billing alarm ($5 threshold)
3. Created IAM user `playground-admin`
4. Created access keys for CLI
5. Configured AWS CLI
6. Verified CLI access with `aws sts get-caller-identity`

## Key Concepts Learned

- **Root account**: The master account created with AWS signup. Should
  rarely be used.
- **IAM user**: A separate identity with specific permissions.
- **MFA**: Multi-factor authentication — requires phone + password.
- **Access keys**: Credentials for programmatic (CLI/API) access.
  Never store in code repositories.
- **Billing alarm**: Sends email notification when charges exceed my $5 threshold.
Default region: us-east-1

## Commands Used

```bash
aws configure                  # Set up CLI credentials
aws sts get-caller-identity    # Verify CLI authentication