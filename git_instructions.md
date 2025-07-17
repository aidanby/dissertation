# Git Repository Setup Instructions

## Current Status
- Your dissertation is now version controlled with Git
- The proposal.bib file has been deleted and replaced with dissertation.bib
- All changes have been committed

## To Push to a Remote Repository

1. Create a new repository on your preferred Git hosting service (GitHub, GitLab, etc.)

2. Add the remote repository to your local Git configuration:
   ```bash
   git remote add origin YOUR_REPOSITORY_URL
   ```
   Replace `YOUR_REPOSITORY_URL` with the actual URL of your remote repository.

3. Push your local repository to the remote:
   ```bash
   git push -u origin main
   ```

## For Amazon Internal Repositories

If you're using an Amazon internal Git repository:

1. Create a new repository in CodeCommit or your preferred internal Git service

2. Add the remote repository:
   ```bash
   git remote add origin ssh://git-codecommit.us-west-2.amazonaws.com/v1/repos/YOUR_REPO_NAME
   ```
   (Adjust the region and repository name as needed)

3. Push your local repository:
   ```bash
   git push -u origin main
   ```

## Verify Your Setup

After pushing, you can verify your remote configuration with:
```bash
git remote -v
```

This should show the URL of your remote repository.