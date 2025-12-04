# GitHub Pages Setup Guide

This guide will help you host your ACH & Wire File Converter on GitHub Pages so everyone can access it online.

## Quick Setup (5 minutes)

### Step 1: Push Your Code to GitHub

If you haven't already:

```bash
# Configure Git (first time only)
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

# Add and commit files
git add index.html Notification.csv README.md .gitignore
git commit -m "Initial commit"

# Create repository on GitHub.com, then:
git remote add origin https://github.com/YOUR_USERNAME/REPO_NAME.git
git branch -M main
git push -u origin main
```

### Step 2: Enable GitHub Pages

1. **Go to your repository on GitHub** (e.g., `https://github.com/YOUR_USERNAME/REPO_NAME`)

2. **Click on "Settings"** (top menu bar)

3. **Scroll down to "Pages"** (left sidebar)

4. **Under "Source"**:
   - Select **"Deploy from a branch"**
   - Branch: **"main"**
   - Folder: **"/ (root)"**
   - Click **"Save"**

5. **Wait 1-2 minutes** for GitHub to build your site

6. **Your site will be live at**:
   ```
   https://YOUR_USERNAME.github.io/REPO_NAME/
   ```

### Step 3: Share Your Site

Once GitHub Pages is enabled, share this URL with your team:
```
https://YOUR_USERNAME.github.io/REPO_NAME/
```

## Example URLs

If your GitHub username is `johndoe` and repository name is `ach-wire-converter`:
- Repository: `https://github.com/johndoe/ach-wire-converter`
- Live Site: `https://johndoe.github.io/ach-wire-converter/`

## Custom Domain (Optional)

If you have a custom domain:

1. In GitHub Pages settings, enter your domain
2. Add a `CNAME` file to your repository with your domain name
3. Configure DNS records with your domain provider

## Updating Your Site

Every time you push changes to the `main` branch, GitHub Pages automatically updates:

```bash
# Make your changes
# Then:
git add .
git commit -m "Update description"
git push
```

The site updates within 1-2 minutes.

## Troubleshooting

### Site shows 404
- Wait 2-3 minutes after enabling Pages
- Check that `index.html` is in the root directory
- Verify the branch is set to `main` (or `master`)

### Changes not showing
- Clear your browser cache (Ctrl+F5)
- Wait a few minutes for GitHub to rebuild
- Check the Actions tab for build errors

### Notification.csv not loading
- Users will need to upload Notification.csv manually (browser security)
- This is expected behavior for client-side file access

## Features Available on GitHub Pages

✅ Full functionality - all features work  
✅ No server required - runs entirely in browser  
✅ Free hosting - unlimited usage  
✅ HTTPS enabled - secure connection  
✅ Custom domain support (optional)  

## Security Note

Since this runs entirely in the browser:
- No data is sent to any server
- Files are processed locally
- All conversions happen on the user's computer
- Perfect for sensitive financial data

## Need Help?

- GitHub Pages Documentation: https://docs.github.com/pages
- Check repository Actions tab for build status
- Verify Settings → Pages shows "Your site is live at..."

