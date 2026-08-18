# Core AWS Concepts — Reference Notes

**Started:** 2026-08-18
**This file grows as I learn new concepts.**

---

## AWS Regions

**What they are:** Physical geographic locations where AWS runs data centers.

**Why they matter:** Resources exist in a specific region. If you look in the
wrong region, your resources appear to be missing.

**My default region:** `us-east-1` (US East — N. Virginia)

**Check your region:**
- In the Console: top-right corner dropdown
- In the CLI: `aws configure list` (look at the "region" row)

**Global vs. Regional services:**
- **Global (same everywhere):** IAM, Route 53, CloudFront
- **Regional (separate per region):** EC2, S3, RDS, Lambda

---

## ARN (Amazon Resource Name)

**What it is:** A unique identifier for every resource in AWS.

**Format:**

arn:aws:[service]:[region]:[account-id]:[resource-type]/[resource-name]

**Examples:**
- IAM user: `arn:aws:iam::123456789012:user/playground-admin`
- S3 bucket: `arn:aws:s3:::my-bucket-name`
- EC2 instance: `arn:aws:ec2:us-east-1:123456789012:instance/i-1234567890abcdef`

**Why ARNs matter:**
- IAM policies use ARNs to specify which resources a permission applies to
- When you see `"Resource": "*"` in a policy, the `*` is a wildcard that
  matches any ARN

---

## JSON Output

**What it is:** The standard format AWS CLI uses to display results.

**Basic structure:**
- `{}` curly braces = an object (key-value pairs)
- `[]` square brackets = an array (a list of items)
- `"text"` double quotes = a string value
- Numbers without quotes = numeric values

**Changing the format:**
- `--output json` = default, structured data
- `--output table` = human-readable table
- `--output text` = plain text, good for scripts

**Filtering output with --query:**
- `--query 'Users[*].UserName'` = get UserName from every item in Users array
- The `*` inside `[]` means "every item"

---

## IAM Key Terms

**User:** A person or application that can log into AWS

**Group:** A collection of users that share the same permissions

**Role:** An identity for AWS services to use (not for humans to log in)

**Policy:** A document defining what actions are allowed or denied

**Principal:** The entity (user, role, service) that is doing something

**Least privilege:** Only grant the minimum permissions needed, nothing more

---

## AWS Services I've Explored

| Service | Type | What it does | My notes |
|---------|------|-------------|----------|
| IAM | Global | Identity and access management | Explored users, policies, roles |
| S3 | Regional | Object/file storage | No buckets yet |
| EC2 | Regional | Virtual servers | No instances yet |
| STS | Global | Identity/token service | Used get-caller-identity |
| CloudShell | Tool | Browser-based terminal | Quick CLI access |
