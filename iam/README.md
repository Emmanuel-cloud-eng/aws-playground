# IAM Practice

This folder contains IAM-related learning materials, policy documents,
and notes.

## Contents

| File | Description |
|------|-------------|
| `iam-notes.md` | Personal reference notes on IAM concepts |
| `s3-readonly-policy.json` | Custom S3 read-only policy created on Day 4 |

## Policies Created

### PlaygroundS3ReadOnly

**Purpose:** Grants read-only access to S3 for learning/auditing accounts.

**Allows:**
- List all S3 buckets (`s3:ListAllMyBuckets`)
- Get bucket location (`s3:GetBucketLocation`)
- List objects in buckets (`s3:ListBucket`)
- Read/download objects (`s3:GetObject`)

**Denies (by omission — no explicit allow):**
- Creating buckets
- Uploading objects
- Deleting anything
- Changing bucket configurations

**Attached to:** `playground-learners` group

**Created via:** AWS Console on YYYY-MM-DD

## Security Notes

- All policies in this folder follow least-privilege principles
- No credentials or secrets are stored here
- Policy files represent IAM policy documents only — not credentials