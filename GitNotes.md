```markdown
Configure your Git cli
```
git config --global user.email "you@example.com"
git config --global user.name "username"
```

# Lina's Git Adventure: A Comprehensive Git and GitHub Tutorial

## Chapter 1: Lina's First Steps with Git

Lina, a curious young programmer, discovered the wonders of Git. She opened her terminal, navigated to her project folder, and initialized her first Git repository:

```bash
$ git init
Initialized empty Git repository in /path/to/linas-project/.git/
```

Lina created a file called "story.txt" and added her first line, "Once upon a time..." She staged her changes:

```bash
$ git add story.txt
```

With a smile, Lina made her first commit:

```bash
$ git commit -m "Begin Lina's story"
[main (root-commit) abc1234] Begin Lina's story
 1 file changed, 1 insertion(+)
 create mode 100644 story.txt
```

Lina checked the status of her repository:

```bash
$ git status
On branch main
nothing to commit, working tree clean
```

She also viewed her commit history:

```bash
$ git log
commit abc1234 (HEAD -> main)
Author: Lina <lina@example.com>
Date:   Fri May 17 14:52:29 2024 +0000

    Begin Lina's story
```

## Chapter 2: Lina's Branch Adventure

As Lina's story grew, she learned about branches. She created a new branch to explore a plot twist:

```bash
$ git branch plot-twist
```

Lina switched to her new branch:

```bash
$ git checkout plot-twist
Switched to branch 'plot-twist'
```

She made changes to "story.txt" and committed them:

```bash
$ git commit -a -m "Add a plot twist"
[plot-twist def5678] Add a plot twist
 1 file changed, 1 insertion(+)
```

Lina then merged her plot twist into the main story:

```bash
$ git checkout main
Switched to branch 'main'

$ git merge plot-twist
Updating abc1234..def5678
Fast-forward
 story.txt | 1 +
 1 file changed, 1 insertion(+)
```

## Chapter 3: Lina Collaborates on GitHub

Excited to share her story, Lina created a GitHub repository. She connected her local repository to GitHub:

```bash
$ git remote add origin <https://github.com/lina/story.git>
```

Lina pushed her story to GitHub:

```bash
$ git push -u origin main
Enumerating objects: 6, done.
Counting objects: 100% (6/6), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (6/6), 487 bytes | 487.00 KiB/s, done.
Total 6 (delta 0), reused 0 (delta 0)
To <https://github.com/lina/story.git>
 * [new branch]      main -> main
Branch 'main' set up to track remote branch 'main' from 'origin'.
```

Lina's friend, Alex, suggested a change. Alex forked Lina's repository on GitHub and cloned it:

```bash
$ git clone <https://github.com/alex/story.git>
Cloning into 'story'...
remote: Enumerating objects: 6, done.
remote: Counting objects: 100% (6/6), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 6 (delta 0), reused 6 (delta 0), pack-reused 0
Receiving objects: 100% (6/6), done.
```

Alex made changes and pushed them to his fork:

```bash
$ git commit -a -m "Improve the story ending"
[main ghi9012] Improve the story ending
 1 file changed, 1 insertion(+)

$ git push origin main
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 298 bytes | 298.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To <https://github.com/alex/story.git>
   def5678..ghi9012  main -> main
```

Alex then created a pull request on GitHub. Lina reviewed the changes and merged them:

```bash
$ git pull origin main
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 3 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), done.
From <https://github.com/lina/story>
 * branch            main       -> FETCH_HEAD
   def5678..ghi9012  main       -> origin/main
Updating def5678..ghi9012
Fast-forward
 story.txt | 1 +
 1 file changed, 1 insertion(+)
```

## Chapter 4: Lina Masters Time Travel

Lina discovered Git's time-traveling powers. She used `git stash` to save unfinished changes:

```bash
$ git stash
Saved working directory and index state WIP on main: ghi9012 Improve the story ending
```

She later applied the stashed changes:

```bash
$ git stash apply
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   story.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

Lina also learned to travel to specific commits using `git checkout`:

```bash
$ git checkout abc1234
Note: switching to 'abc1234'.

You are in 'detached HEAD' state...

HEAD is now at abc1234 Begin Lina's story
```

## Chapter 5: Lina's Advanced Git Techniques

### Git Rebase:
Lina discovered that `git rebase` is a powerful tool for keeping her commit history clean and linear. It allows her to change the base of her branch, effectively rewriting the commit history to make it appear as if she had started her work from a different point.

Benefits of Git Rebase:

1. Clean and Linear History: Rebasing creates a cleaner, more linear commit history compared to merging. It makes the commit history look as if the feature branch was developed after the latest commits on the base branch, even if it was developed simultaneously. This can make the history easier to understand and navigate.
2. Avoid Unnecessary Merge Commits: When you merge a feature branch into the main branch, Git creates a merge commit to tie the histories together. If you frequently merge small features or bug fixes, your commit history can become cluttered with merge commits. Rebasing eliminates these unnecessary merge commits, keeping the history concise and focused on the actual changes.
3. Maintain a Single Narrative: Rebasing allows you to maintain a single, clear narrative in your commit history. By rewriting the commits on your feature branch to appear as if they were made after the latest commits on the base branch, you can present a more coherent story of how your project evolved.
4. Easier Conflict Resolution: When you rebase, conflicts are resolved on a commit-by-commit basis as Git applies each commit from your feature branch onto the base branch. This can make conflict resolution more manageable compared to resolving all conflicts at once during a merge.

Example:
Let's say Lina is working on a new feature in a branch called "new-character". Meanwhile, her friend Alex has made some changes to the "main" branch. Here's what their commit history looks like:

```
      A---B---C new-character
     /
D---E---F---G main
```

Lina wants to rebase her "new-character" branch onto the latest commit of the "main" branch. Here's what she does:

```bash
$ git checkout new-character
$ git rebase main
First, rewinding head to replay your work on top of it...
Applying: Add new character
Applying: Develop new character
Applying: Resolve new character's story
```

After the rebase, the commit history will look like this:

```
              A'--B'--C' new-character
             /
D---E---F---G main
```

Git has rewritten the commits from the "new-character" branch (A, B, C) as if they happened after the latest commit on the "main" branch (G). The new commits (A', B', C') have different commit hashes because their parent commit has changed, but the actual changes in each commit remain the same.

Now, when Lina merges her "new-character" branch back into "main", there will be no merge commit, and the history will remain clean and linear:

```bash
$ git checkout main
$ git merge new-character
Updating G..C'
Fast-forward
 story.txt | 3 +++
 1 file changed, 3 insertions(+)
```

The resulting history will be:

```
D---E---F---G---A'--B'--C' main
```

### Git Bisect:
`git bisect` is a powerful tool that helps Lina find the specific commit that introduced a bug or regression in her code. It performs a binary search through the commit history to efficiently identify the problematic commit.

Let's say Lina discovers a bug in her story, but she's not sure which commit caused it. She starts the bisect process with:

```bash
$ git bisect start
$ git bisect bad
$ git bisect good abc1234
Bisecting: 2 revisions left to test after this (roughly 1 step)
[def5678] Add a plot twist
```

Here, Lina marks the current commit as "bad" (containing the bug) and specifies a known "good" commit (abc1234) where the bug didn't exist. Git then selects a commit in the middle of this range (def5678) and checks it out for Lina to test.

Lina checks if the bug exists in this commit and marks it as "good" or "bad" using `git bisect good` or `git bisect bad`, respectively. Git then selects another commit to test based on her feedback. This process continues until Git identifies the specific commit that introduced the bug.

Once the buggy commit is found, Lina can examine the changes made in that commit to understand and fix the issue. She then ends the bisect session with:

```bash
$ git bisect reset
Previous HEAD position was def5678 Add a plot twist
Switched to branch 'main'
```

This resets her repository to the original state before the bisect process.

By mastering these advanced Git techniques, Lina can efficiently manage her project's history, collaborate with others, and troubleshoot issues effectively.

```bash
$ git bisect reset
Previous HEAD position was def5678 Add a plot twist
Switched to branch 'main'
```

### Git Cherry-Pick:
`git cherry-pick` is a powerful command that allows Lina to select individual commits from one branch and apply them to another branch. This is useful when Lina wants to include specific changes from a branch without merging the entire branch.

Example:
Let's say Lina has two branches in her repository: "main" and "experimental". The "experimental" branch contains several commits, but Lina only wants to apply one specific commit (abc1234) to her "main" branch. Here's what the commit history looks like:

```
      A---B---C---D experimental
     /
E---F---G main
```

To cherry-pick the commit (abc1234) from the "experimental" branch and apply it to the "main" branch, Lina follows these steps:

```bash
$ git checkout main
$ git cherry-pick abc1234
[main jkl5678] Begin Lina's story
 Date: Fri May 17 14:52:29 2024 +0000
 1 file changed, 1 insertion(+)
 create mode 100644 story.txt
```

Let's break down the output:

- `[main jkl5678]`: This indicates that a new commit has been created on the "main" branch with the hash "jkl5678".
- `Begin Lina's story`: This is the commit message from the original commit (abc1234) that was cherry-picked.
- `Date: Fri May 17 14:52:29 2024 +0000`: This is the timestamp of the original commit.
- `1 file changed, 1 insertion(+)`: This shows the number of files modified and the number of lines added or removed in the cherry-picked commit.
- `create mode 100644 story.txt`: This indicates that a new file named "story.txt" was created in the cherry-picked commit.

After the cherry-pick operation, the commit history will look like this:

```
      A---B---C---D experimental
     /
E---F---G---H main
```

The new commit (H) on the "main" branch contains the changes from the cherry-picked commit (abc1234), but it has a different commit hash (jkl5678) because it has a different parent commit.

Benefits of Git Cherry-Pick:

1. Selective Integration: Cherry-picking allows Lina to selectively integrate specific changes from one branch to another without merging the entire branch. This is useful when Lina wants to include only certain commits or when she wants to avoid bringing in unrelated changes.
2. Targeted Bug Fixes: If a bug fix is committed on one branch, Lina can use `git cherry-pick` to apply that fix to other branches without merging the entire branch.
3. Experimental Features: If Lina is working on an experimental feature in a separate branch and discovers a useful change that she wants to include in the main branch, she can use `git cherry-pick` to apply that specific commit without merging the entire experimental branch.

Considerations:

- Cherry-picking can lead to duplicate commits if the same change is later merged from the original branch. Lina should use cherry-picking judiciously and communicate with her team to avoid confusion.
- If the cherry-picked commit depends on earlier commits in its original branch, Lina may need to cherry-pick those commits as well to maintain a consistent history.

By using `git cherry-pick`, Lina can selectively apply specific commits from one branch to another, giving her fine-grained control over the changes she includes in her project.

## Chapter 6: Lina's Git Troubleshooting

### Git Reflog:
`git reflog` is a powerful command that allows Lina to view the history of her repository, including all the actions she has performed. It keeps track of every change to the HEAD pointer, which is a reference to the current branch or commit.

Example:
Let's say Lina has been working on her story and realizes she accidentally deleted an important commit. She can use `git reflog` to view the history of her actions:

```bash
$ git reflog
jkl5678 (HEAD -> main) HEAD@{0}: cherry-pick: Begin Lina's story
ghi9012 HEAD@{1}: rebase finished: returning to refs/heads/main
ghi9012 HEAD@{2}: rebase: Add a plot twist
def5678 HEAD@{3}: commit: Add a plot twist
abc1234 HEAD@{4}: commit: Begin Lina's story
...
```

Let's break down the output:

- Each line represents an action that modified the HEAD pointer.
- The commit hash (e.g., jkl5678, ghi9012) identifies the commit that HEAD pointed to after each action.
- `(HEAD -> main)` indicates the current position of the HEAD pointer and the current branch.
- `HEAD@{0}`, `HEAD@{1}`, etc., represent the position of HEAD in the reflog history.
- The action performed is described after the colon (e.g., cherry-pick, rebase, commit).

If Lina wants to recover a deleted commit, she can find the corresponding entry in the reflog and use `git checkout` to move HEAD to that commit:

```bash
$ git checkout abc1234
Note: checking out 'abc1234'.

You are in 'detached HEAD' state...
```

Now, Lina can create a new branch from this commit to restore the lost changes:

```bash
$ git branch recovered-branch
```

Benefits of Git Reflog:

1. Recovery: Reflog allows Lina to recover lost commits, branches, or changes that she may have
