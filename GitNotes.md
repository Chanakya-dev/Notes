Chapter 1: First Steps with Git
Open your terminal and navigate to your project folder.

Initialize your first Git repository:


git init
Create a file called "story.txt" and add your first line, "Once upon a time..."

Stage your changes:


git add story.txt
Make your first commit:

bash
Copy code
git commit -m "Begin Lina's story"
Check the status of your repository:

bash
Copy code
git status
View your commit history:

bash
Copy code
git log
Chapter 2: Branching
Create a new branch to explore a plot twist:

bash
Copy code
git branch plot-twist
Switch to your new branch:

bash
Copy code
git checkout plot-twist
Make changes to "story.txt" and commit them:

bash
Copy code
git add story.txt
git commit -m "Add a plot twist"
Merge your plot twist into the main story:

bash
Copy code
git checkout main
git merge plot-twist
Chapter 3: Collaborate on GitHub
Create a GitHub repository.

Configure Git with your username and email:

bash
Copy code
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
Connect your local repository to GitHub (replace <username> and <token> with your GitHub username and personal access token):

bash
Copy code
git remote add origin https://github.com/lina/story.git
git remote set-url origin https://<username>:<token>@github.com/lina/story.git
git push -u origin main
Your friend, Alex, can contribute to your story by forking your repository on GitHub and cloning it locally:

bash
Copy code
git clone https://github.com/alex/story.git
Alex makes changes, commits them, and pushes to his forked repository:

bash
Copy code
echo "Improve the story ending" >> story.txt
git add story.txt
git commit -m "Improve the story ending"
git push origin main
Alex creates a pull request on GitHub for you to review and merge.

After merging the pull request, pull the latest changes to your local repository:

bash
Copy code
git pull origin main
Chapter 4: Pull Requests
Open your project on GitHub and click on the "Pull requests" tab.

Click "New pull request".

Compare changes between branches (e.g., main and feature-branch).

Add a title and description for your pull request, then click "Create pull request".

Review comments and code changes.

Merge the pull request once it's reviewed and approved:

bash
Copy code
git pull origin main
Chapter 5: Time Travel with Git
Use git stash to save unfinished changes:

bash
Copy code
git stash
Later, apply the stashed changes:

bash
Copy code
git stash apply
Travel to a specific commit using git checkout:

bash
Copy code
git checkout <commit-hash>
Cherry-pick a specific commit from one branch to another:

bash
Copy code
git checkout main
git cherry-pick <commit-hash>
Chapter 6: Troubleshooting with Git
Use git reflog to view the history of your repository:

bash
Copy code
git reflog
Recover a deleted commit by checking out the corresponding commit hash from the reflog:

bash
Copy code
git checkout <commit-hash>
git branch recovered-branch
Use git bisect to find the commit that introduced a bug:

bash
Copy code
git bisect start
git bisect bad
git bisect good <good-commit-hash>
Test each commit Git presents and mark it as "good" or "bad" until the buggy commit is found.

End the bisect session:

bash
Copy code
git bisect reset
To revert files to the state from a specific commit:

bash
Copy code
git reset <commit-hash>
git restore --source=<commit-hash> --staged --worktree .
git commit -m "Revert files to state from the specified commit"
Chapter 7: Handling Merge Conflicts
Create a new branch for a new change:

bash
Copy code
git branch new-change
git checkout new-change
Make changes to "story.txt" and commit them:

bash
Copy code
echo "Lina met a dragon." >> story.txt
git add story.txt
git commit -m "Add dragon encounter"
Switch back to the main branch and make conflicting changes:

bash
Copy code
git checkout main
echo "Lina found a treasure." >> story.txt
git add story.txt
git commit -m "Add treasure discovery"
Attempt to merge the new change into the main branch:

bash
Copy code
git merge new-change
Resolve the conflict by editing "story.txt":

plaintext
Copy code
<<<<<<< HEAD
Lina found a treasure.
=======
Lina met a dragon.
>>>>>>> new-change
Choose which changes to keep or combine them, then stage and commit the resolution:

bash
Copy code
git add story.txt
git commit -m "Resolve merge conflict between treasure and dragon"
Chapter 8: GitLens Essentials
GitLens is a powerful extension for Visual Studio Code that enhances Git capabilities. Here are some main concepts:

Installation:

Install GitLens from the Visual Studio Code Marketplace.
Blame Annotation:

View who made changes to the current line or block of code.
Hover over a line of code to see the author, commit message, and time of the change.
File History:

View the commit history of a file.
Right-click on a file and select "GitLens: Show File History".
Line History:

View the commit history of a specific line or block of code.
Right-click on a line and select "GitLens: Show Line History".
Diff Comparison:

Compare changes between commits, branches, or your working directory.
Use the "GitLens: Compare" command to start a comparison.
Commit Details:

View detailed information about a specific commit.
Hover over a commit in the GitLens sidebar to see its details.
By following this tutorial step by step, you'll gain a solid understanding of essential Git concepts and commands. Practice regularly, and you'll soon become comfortable with using Git for version control and collaboration.
