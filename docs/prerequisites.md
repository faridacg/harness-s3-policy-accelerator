# Prerequisites

## Harness
- Harness account (Free tier works)
- Project Admin role minimum
- Harness account with Cloud runner access
  (enabled by defalut on all plans - no setup needed)

## GitHub
- GitHub account
- Personal Access Token (PAT) with scopes:
  - repo
  - workflow
  - read:org

## AWS
- AWS account
- IAM user with permissions:
  - s3:*
  - ec2:DescribeRegions

## Microsoft Teams
- Teams channel with Incoming Webhook configured

## Harness Secrets Required

| Secret Name | Description |
|---|---|
| github_pat | GitHub Personal Access Token |
| aws_access_key_id | AWS Access Key ID |
| aws_secret_access_key | AWS Secret Access Key |
| teams_webhook_url | Microsoft Teams Webhook URL |
