# Setup Guide

## Step 1: Fork or Clone This Repository
Fork this repo into your GitHub account.

## Step 2: Copy GitHub Actions Workflow
Copy github-actions/create-s3-bucket.yml into your repo under:
.github/workflows/create-s3-bucket.yml

## Step 3: Add GitHub Secrets
In your GitHub repo → Settings → Secrets → Actions:
- AWS_ACCESS_KEY_ID
- AWS_SECRET_ACCESS_KEY

## Step 4: Add Harness Secrets
In Harness → Account Settings → Secrets:
- github_pat
- teams_webhook_url
- aws_access_key_id
- aws_secret_access_key

## Step 5: Import Step Templates into Harness
1. Go to Project Settings → Templates
2. Click + New Template → Step
3. Switch to YAML view
4. Paste content from:
   - harness-templates/step-templates/s3-policy-warn-only.yaml
   - harness-templates/step-templates/s3-policy-blocking.yaml
5. Save each as version v1

## Step 6: Import Pipeline Templates into Harness
1. Go to Project Settings → Templates
2. Click + New Template → Pipeline
3. Switch to YAML view
4. Paste content from:
   - step-templates/s3-provisioning-warn-only.yaml
   - step-templates/s3-provisioning-blocking.yaml
5. Save each as version v1

## Step 7: Create Pipeline from Template
1. Go to Pipelines → + Create Pipeline
2. Select "From Template"
3. Choose warn-only or blocking version
4. Fill in your GitHub repo and Teams webhook details
5. Run!

## Naming Conventions Enforced
| Rule | Description |
|---|---|
| Lowercase only | my-bucket not My-Bucket |
| Min 5 characters | dev-bucket not bkt |
| Hyphens only | dev-bucket not dev_bucket |
| Environment prefix | Must start with dev/staging/prod/test |
| Private visibility | Public buckets trigger warning or block |
