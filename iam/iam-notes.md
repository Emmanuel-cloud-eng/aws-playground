# IAM — Identity and Access Management

**Date created:** 2026-08-19
**Last updated:** 2026-08-19

---

## What Is IAM?

(Write your own explanation of what IAM is and why it matters)

---

## The Golden Rule of AWS Security

**Everything is denied by default.**

(Write what this means in your own words and why it matters)

---

## The Four Building Blocks

### 1. Users

**What they are:** (your description)

**When to create one:** (your answer)

**Properties a user can have:**
- (list them)

**My current users:**
| Username | Purpose | Has MFA? | Has Access Keys? |
|----------|---------|---------|-----------------|
| playground-admin | Daily learning and CLI access | No | Yes |

---

### 2. Groups

**What they are:** (your description)

**Why they exist:** (your answer — think about the 20 developers example)

**Important limitations:**
- (list what groups cannot do)

**My current groups:**
| Group Name | Members | Policies Attached |
|-----------|---------|------------------|
| playground-learners | 0 | PlaygroundS3ReadOnly |

---

### 3. Policies

**What they are:** (your description)

**Types of policies:**
| Type | Created by | Can I edit it? |
|------|-----------|---------------|
| AWS Managed | Amazon | No |
| Customer Managed | Me | Yes |
| Inline | Me | Yes (but avoid) |

**Policy structure:**
```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "optional-label",
            "Effect": "Allow or Deny",
            "Action": ["service:Action"],
            "Resource": "arn or *"
        }
    ]
}
```


## What each field means:

Version: (your description)
Statement: (your description)
Sid: (your description)
Effect: (your description — what are the only two values?)
Action: (your description — what format do actions use?)
Resource: (your description — what is the difference between * and a specific ARN?)
S3 ARN format:

Bucket level: arn:aws:s3:::bucket-name
Object level: arn:aws:s3:::bucket-name/*
Any bucket: arn:aws:s3:::*
Any object in any bucket: arn:aws:s3:::*/*
My custom policies:

## Policy Name	What it allows	Attached to
PlaygroundS3ReadOnly	List buckets, list objects, read objects	playground-learners group
4. Roles

What they are: (your description)

Key difference from users: (your explanation)

Who assumes roles:

(list the types of things that assume roles)
Two parts of a role:

Trust policy: (your description)
Permissions policy: (your description)
When I'll use roles:

(examples from what you learned today)
How AWS Evaluates Permissions

The decision flow:

(first thing AWS checks)
(second thing AWS checks)
(what happens if no matching allow is found)
Key concept — Implicit Deny:
(Write what this means in your own words)

Key concept — Explicit Deny:
(An explicit "Effect": "Deny" in a policy ALWAYS wins, even if another
policy has an Allow for the same action. Write what this means in your words.)

IAM Best Practices I've Learned

 Enable MFA on root account ✅ (done Day 1)
 Never use root for daily work ✅ (using playground-admin)
 Create IAM users for people, roles for services
 Use groups to manage permissions for multiple users
 Apply least privilege — only grant what's needed
 Regularly review the IAM credential report
 Rotate access keys regularly (every 90 days)
 Never put access keys in code or commit them to GitHub
Tools for IAM

Tool	What it does	When to use it
IAM Console	Visual interface for managing IAM	Exploration and setup
IAM Policy Simulator	Test what a policy allows/denies	Before deploying a policy
Credential Report	Shows security status of all users	Security audits
Access Advisor	Shows which services a user has actually used	Cleaning up unused permissions
Commands for IAM (CLI)

Bash

# List all IAM users
aws iam list-users

# List groups for a user
aws iam list-groups-for-user --user-name playground-admin

# List policies attached to a user
aws iam list-attached-user-policies --user-name playground-admin

# List policies attached to a group
aws iam list-attached-group-policies --group-name playground-learners

# Get account security summary
aws iam get-account-summary

# List all groups
aws iam list-groups
Things That Confused Me

(Write honestly — these are the things to study further)

Questions I Still Have

(Write genuine questions — they guide your learning roadmap)## Commands for IAM (CLI) — With Expected Output

```bash
# List all groups
aws iam list-groups
# Expected: JSON array of group objects

# List policies on a group
aws iam list-attached-group-policies --group-name playground-learners
# Expected: JSON array of attached policy names and ARNs

# Get group details including members
aws iam get-group --group-name playground-learners
# Expected: Group metadata + list of Users (empty if no members)

# Get policy metadata
aws iam get-policy --policy-arn YOUR_POLICY_ARN
# Expected: Policy details including AttachmentCount and DefaultVersionId

# Get the actual policy document
aws iam get-policy-version --policy-arn YOUR_POLICY_ARN --version-id v1
# Expected: The raw JSON policy document