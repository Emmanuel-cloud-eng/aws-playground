# AWS Playground — Learning Log

## Day 1 — 2026-08-15

**Time spent:** ~2 hours

### What I did:
- Set up GitHub repository
- Created folder structure
- Secured AWS account (MFA, billing alarm, IAM user)
- Configured AWS CLI
- Made first Git commits

### What I learned:
- Git workflow: status → add → commit → push
- AWS root account vs. IAM user
- Why MFA and billing alerts matter
- How .gitignore protects secrets

### What confused me:
- I think I need to polish my linux had to look up a lot of commands to proceed

### Next steps:
- Practice Git workflow
- Learn S3 basics 

## Day 2 — 2026-08-16

**Time spent:** ~2 hours

### What I did:
- Practiced git status, add, commit, push, diff, log
- Made multiple commits with good messages
- Practiced safe undo with git restore
- Created personal Git workflow documentation



### Next steps:
- Day 3: AWS Console navigation and CLI basics


## Day 3 — 2026-08-18

**Time spent:** ~4 hours

### What I did:
- Explored AWS Console: IAM, S3, EC2 dashboards
- Learned what Regions, ARNs, AMIs, Security Groups, and Key Pairs are
- Ran first AWS CLI commands: get-caller-identity, list-users, s3 ls, describe-instances
- Explored AWS CloudShell
- Created CLI command cheat sheet
- Created AWS concepts reference notes

### Commands I can now run from memory:
- `aws sts get-caller-identity`
- `aws iam list-users`
- `aws s3 ls`
- `aws ec2 describe-instances`
- `aws iam get-account-summary`

### What clicked today:
- JSON ouputs really put things neatly



### Next steps:
- Day 4: IAM deep dive — create groups, explore policies