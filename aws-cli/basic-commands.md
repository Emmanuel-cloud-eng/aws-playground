# AWS CLI Basic Commands — Reference Sheet

**Created:** 2026-08-18
**AWS Region:** us-east-1
**IAM User:** playground-admin

---

## CLI Command Structure

Every AWS CLI command follows this pattern:

aws [service] [action] [--option value]


Examples:
- `aws sts get-caller-identity`
- `aws iam list-users`
- `aws s3 ls`

---

## Output Format Options

Add `--output` to any command to change the display format:

| Flag | Format | Best for |
|------|--------|----------|
| `--output json` | JSON (default) | Scripting and detailed reading |
| `--output table` | Formatted table | Human reading |
| `--output text` | Tab-separated | Combining with other tools |

---

## Identity and Security (STS)

### Who am I?
```bash
aws sts get-caller-identity

What it does: Asks the CLI what account am I currently using
When to use it: To check which AWS account you are in.
Key fields in the output:

UserId: Your Unique account User ID
Account: Log in name of your account
Arn: Amazon resource name, unique identifier for all resources in aws, S3, EC2 all have it

IAM Commands
List all IAM users
aws iam list-users
What it does: List all IAM users you have created so far.

List policies attached to a user
aws iam list-attached-user-policies --user-name playground-admin
What it does: List all policies attached to the username "playgroung.

```

---

### List policies attached to a user

Bash

`aws iam list-attached-user-policies --user-name playground-admin`
What it does: Get the policies attached to the Username playground-admin
The --user-name flag: specifies the username

## Get account summary

Bash

`aws iam get-account-summary`
What it does: Gives an overview of your account
Key security fields to check:

AccountMFAEnabled: should be 1
AccountAccessKeysPresent: should be 0
S3 Commands

## List all buckets

Bash

`aws s3 ls` 
What it does: List the buckets you've created if any
Expected output on a new account: no response on terminal meaning empty

## List buckets in a specific region

Bash

`aws s3 ls --region us-east-1`
What it does: List buckects you've created in a specific region

EC2 Commands

## List all instances

Bash

`aws ec2 describe-instances`
What it does: list all your instances luanched together
Expected output on a new account: {"Reservations": []}

## List security groups (names only)

Bash
``` aws ec2 describe-security-groups \
  --query 'SecurityGroups[*].GroupName' \
  --output text 
  ```
What it does: filters the security group of a specified group name
What --query does: ses a language called JMESPath (pronounced "James path"). It lets you extract just the parts of the JSON you want.


## Getting Help

Help for a service

Bash

`aws [service] help`
Help for a specific action

Bash

`aws [service] [action] help`
## Useful Flags

Flag	Example	What it does
--output	--output table	Change output format
--region	--region eu-west-1	Target a different region
--query	--query 'Users[*].UserName'	Filter JSON output
--profile	--profile myprofile	Use a named credential profile


## My Observations


Commands I'll use most often: I don't know yet since I just started 


Questions I still have:
I want to practice more of this more tomorrow