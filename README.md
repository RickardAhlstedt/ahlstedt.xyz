# ahlstedt.xyz

Hugo-based personal blog and portfolio website.

## Development

This repository uses a development branch workflow:
- `main` branch: Production-ready code
- `development` branch: Active development

### Creating the Development Branch

To create and set up the development branch:

```bash
# Create development branch from main
git checkout main
git pull
git checkout -b development
git push -u origin development
```

Once created, use the development branch for all active development work, and merge to main when ready to deploy.

## Deployment

The site is automatically deployed to an FTP server when changes are pushed to the `main` branch.

### Required GitHub Secrets

The following secrets need to be configured in the repository settings for the FTP deployment to work:

1. `FTP_SERVER` - The FTP server hostname (e.g., `ftp.example.com`)
2. `FTP_USERNAME` - The FTP username
3. `FTP_PASSWORD` - The FTP password
4. `FTP_REMOTE_DIR` - The remote directory path on the FTP server where files should be uploaded

To configure these secrets:
1. Go to repository Settings → Secrets and variables → Actions
2. Click "New repository secret"
3. Add each of the above secrets with their corresponding values

## Local Development

To build the site locally:

```bash
# Install Hugo (if not already installed)
# See: https://gohugo.io/installation/

# Clone the repository with submodules
git clone --recurse-submodules https://github.com/RickardAhlstedt/ahlstedt.xyz

# Build the site
hugo

# Or run development server
hugo server -D
```

## Theme

This site uses the [PaperMod](https://github.com/adityatelange/hugo-PaperMod) theme.
