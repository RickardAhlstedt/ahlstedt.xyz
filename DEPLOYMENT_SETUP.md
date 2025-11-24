# Deployment Setup Instructions

This document provides instructions for setting up the automated Hugo FTP deployment workflow.

## Overview

The repository is now configured with a GitHub Actions workflow that will automatically:
1. Build your Hugo site when you push to the `main` branch
2. Upload the generated files to your FTP server

## Required Setup Steps

### 1. Create the Development Branch

The development branch needs to be created manually:

```bash
# Switch to main branch
git checkout main
git pull

# Create development branch
git checkout -b development

# Push to remote
git push -u origin development
```

After this is set up:
- Use the `development` branch for ongoing work
- Merge to `main` when ready to deploy to production
- The workflow will automatically deploy when changes are pushed to `main`

### 2. Configure GitHub Secrets

You need to add the following secrets to your GitHub repository:

1. Go to your repository on GitHub
2. Click on **Settings** → **Secrets and variables** → **Actions**
3. Click **New repository secret**
4. Add each of the following secrets:

| Secret Name | Description | Example |
|------------|-------------|---------|
| `FTP_SERVER` | Your FTP server hostname | `ftp.yourhost.com` |
| `FTP_USERNAME` | Your FTP username | `username@yourhost.com` |
| `FTP_PASSWORD` | Your FTP password | `your-secure-password` |
| `FTP_REMOTE_DIR` | Remote directory path on FTP server | `/public_html/` or `/htdocs/` |

**Note:** You mentioned you will configure the `FTP_REMOTE_DIR` later, but it needs to be set before the workflow runs successfully.

### 3. Test the Deployment

Once the secrets are configured:

1. Make a small change on the `main` branch (or merge from `development`)
2. Push to GitHub
3. Go to **Actions** tab in your repository
4. You should see the workflow running
5. Check the logs to ensure it completes successfully

## Workflow Details

The workflow (`.github/workflows/deploy.yml`) will:
- Trigger only on push to `main` branch
- Use Hugo extended version (latest)
- Build the site with minification
- Upload the `public/` directory to your FTP server

## Troubleshooting

If the deployment fails:

1. **Check GitHub Actions logs**: Go to Actions tab → Click on the failed workflow → Review the logs
2. **Verify secrets**: Ensure all four secrets are correctly set
3. **Test FTP connection**: Verify your FTP credentials work by testing with an FTP client
4. **Check remote directory**: Ensure `FTP_REMOTE_DIR` exists on your server and you have write permissions

## Security Notes

- Never commit FTP credentials to the repository
- Secrets are encrypted and only accessible during workflow runs
- Consider using FTPS or SFTP for better security (may require different action)
