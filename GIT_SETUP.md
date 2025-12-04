# Git Setup Instructions

Follow these steps to push your project to GitHub (or another Git hosting service).

## Step 1: Configure Git (First Time Only)

If you haven't set up Git before, configure your identity:

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

## Step 2: Create a GitHub Repository

1. Go to [GitHub.com](https://github.com) and sign in
2. Click the **"+"** icon in the top right → **"New repository"**
3. Name your repository (e.g., `ach-wire-converter`)
4. Choose **Public** or **Private**
5. **DO NOT** initialize with README, .gitignore, or license (we already have these)
6. Click **"Create repository"**

## Step 3: Add Files and Commit

The repository is already initialized. Now commit your files:

```bash
# Stage all important files
git add index.html Notification.csv README.md .gitignore

# Commit the files
git commit -m "Initial commit: ACH and Wire file converter"
```

## Step 4: Connect to GitHub and Push

After creating the repository on GitHub, you'll see instructions. Use these commands:

```bash
# Add the remote repository (replace YOUR_USERNAME and REPO_NAME)
git remote add origin https://github.com/YOUR_USERNAME/REPO_NAME.git

# Rename the default branch to main (if needed)
git branch -M main

# Push your code to GitHub
git push -u origin main
```

## Alternative: Using GitHub Desktop

If you prefer a graphical interface:

1. Download [GitHub Desktop](https://desktop.github.com/)
2. Sign in with your GitHub account
3. Click **File → Add Local Repository**
4. Select the `C:\New folder` directory
5. Click **Publish repository** to push to GitHub

## Alternative: Using GitHub CLI

If you have GitHub CLI installed:

```bash
# Authenticate (first time only)
gh auth login

# Create and push repository
gh repo create ach-wire-converter --public --source=. --remote=origin --push
```

## Updating the Repository

After making changes:

```bash
# Stage changes
git add .

# Commit changes
git commit -m "Description of your changes"

# Push to GitHub
git push
```

## Sharing the Repository

Once pushed to GitHub, share the repository URL:
```
https://github.com/YOUR_USERNAME/REPO_NAME
```

Others can:
- View the code online
- Download the files
- Clone the repository: `git clone https://github.com/YOUR_USERNAME/REPO_NAME.git`

## GitHub Pages (Optional - Host the App Online)

To host the app directly on GitHub:

1. Go to your repository on GitHub
2. Click **Settings** → **Pages**
3. Under **Source**, select **main** branch and **/ (root)** folder
4. Click **Save**
5. Your app will be available at: `https://YOUR_USERNAME.github.io/REPO_NAME/`

> **Note**: For GitHub Pages, you may need to rename `index.html` or adjust the file structure.

## Troubleshooting

### "Permission denied" error
- Make sure you're authenticated with GitHub
- Use a Personal Access Token instead of password (GitHub no longer accepts passwords)

### "Repository not found" error
- Check that the repository name and username are correct
- Verify you have push access to the repository

### Need to change the remote URL
```bash
git remote set-url origin https://github.com/YOUR_USERNAME/REPO_NAME.git
```

