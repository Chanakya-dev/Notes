#  A Comprehensive Git and GitHub Tutorial

## Chapter 1: First Steps with Git

1. Open your terminal and navigate to your project folder.

2. Initialize your first Git repository:

   ```bash
   git init
   ```

3. Create a file called "story.txt" and add your first line, "Once upon a time..."

4. Stage your changes:

   ```bash
   git add story.txt
   ```

5. Make your first commit:

   ```bash
   git commit -m "Begin Lina's story"
   ```

6. Check the status of your repository:

   ```bash
   git status
   ```

7. View your commit history:

   ```bash
   git log
   ```

## Chapter 2: Branching

1. Create a new branch to explore a plot twist:

   ```bash
   git branch plot-twist
   ```

2. Switch to your new branch:

   ```bash
   git checkout plot-twist
   ```

3. Make changes to "story.txt" and commit them:

   ```bash
   git add story.txt
   git commit -m "Add a plot twist"
   ```

4. Merge your plot twist into the main story:

   ```bash
   git checkout main
   git merge plot-twist
   ```

## Chapter 3: Collaborate on GitHub

1. Create a GitHub repository.

2. Configure Git with your username and email:

   ```bash
   git config --global user.name "Your Name"
   git config --global user.email "your@email.com"
   ```

3. Connect your local repository to GitHub (replace `<username>` and `<token>` with your GitHub username and personal access token):

   ```bash
   git remote add origin https://github.com/lina/story.git
   git remote set-url origin https://<username>:<token>@github.com/lina/story.git
   git push -u origin main
   ```

4. Your friend, Alex, can contribute to your story by forking your repository on GitHub and cloning it locally:

   ```bash
   git clone https://github.com/alex/story.git
   ```

5. Alex makes changes, commits them, and pushes to his forked repository:

   ```bash
   echo "Improve the story ending" >> story.txt
   git add story.txt
   git commit -m "Improve the story ending"
   git push origin main
   ```

6. Alex creates a pull request on GitHub for you to review and merge.

7. After merging the pull request, pull the latest changes to your local repository:

   ```bash
   git pull origin main
   ```

## Chapter 4: Pull Requests

1. Open your project on GitHub and click on the "Pull requests" tab.

2. Click "New pull request".

3. Compare changes between branches (e.g., main and feature-branch).

4. Add a title and description for your pull request, then click "Create pull request".

5. Review comments and code changes.

6. Merge the pull request once it's reviewed and approved:

   ```bash
   git pull origin main
   ```

## Chapter 5: Time Travel with Git
. Use `git stash` to save unfinished changes:

   ```bash
   git stash
   ```

2. Later, apply the stashed changes:

   ```bash
   git stash apply
   ```

3. Travel to a specific commit using `git checkout`:

   ```bash
   git checkout <commit-hash>
   ```

4. Cherry-pick a specific commit from one branch to another:

   ```bash
   git checkout main
   git cherry-pick <commit-hash>
   ```
1

## Chapter 6: Troubleshooting with Git

1. Use `git reflog` to view the history of your repository:

   ```bash
   git reflog
   ```

2. Recover a deleted commit by checking out the corresponding commit hash from the reflog:

   ```bash
   git checkout <commit-hash>
   git branch recovered-branch
   ```

3. Use `git bisect` to find the commit that introduced a bug:

   ```bash
   git bisect start
   git bisect bad
   git bisect good <good-commit-hash>
   ```

4. Test each commit Git presents and mark it as "good" or "bad" until the buggy commit is found.

5. End the bisect session:

   ```bash
   git bisect reset
   ```


## Chapter 7: Handling Merge Conflicts

1. Create a new branch for a new change:

   ```bash
   git branch new-change
   git checkout new-change
   ```

2. Make changes to "story.txt" and commit them:

   ```bash
   echo "Lina met a dragon." >> story.txt
   git add story.txt
   git commit -m "Add dragon encounter"
   ```

3. Switch back to the main branch and make conflicting changes:

   ```bash
   git checkout main
   echo "Lina found a treasure." >> story.txt
   git add story.txt
   git commit -m "Add treasure discovery"
   ```

4. Attempt to merge the new change into the main branch:

   ```bash
   git merge new-change
   ```

5. Resolve the conflict by editing "story.txt":

   ```plaintext
   <<<<<<< HEAD
   Lina found a treasure.
   =======
   Lina met a dragon.
   >>>>>>> new-change
   ```

6. Choose which changes to keep or combine them, then stage and commit the resolution:

   ```bash
   git add story.txt
   git commit -m "Resolve merge conflict between treasure and dragon"
   ```

## Chapter 8: GitLens Essentials

GitLens is a powerful extension for Visual Studio Code that enhances Git capabilities. Here are some main concepts:

- Installation:
  - Install GitLens from the Visual Studio Code Marketplace.
- Blame Annotation:
  - View who made changes to the current line or block of code.
  - Hover over a line of code to see the author, commit message, and time of the change.
- File History:
  - View the commit history of a file.
  - Right-click on a file and select "GitLens: Show File History".
- Line History:
  - View the commit history of a specific line or block of code.
  - Right-click on a line and select "GitLens: Show Line History".
- Diff Comparison:
  - Compare changes between commits, branches, or your working directory.
  - Use the "GitLens: Compare" command to start a comparison.
- Commit Details:
  - View detailed information about a specific commit.
  - Hover over a commit in the GitLens sidebar to see its details.


## Demo of git fetch.
go to github do some changes to a file online.
```
git fetch

```
## refer gitlense to see the difference.
