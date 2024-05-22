Hackathon Question: Git and GitHub Adventure
# Hackathon Question: Git and GitHub Adventure

## Objective:
In this hackathon, participants will apply their knowledge of Git and GitHub to collaborate on a story-writing project. They will create branches, make commits, resolve merge conflicts, and use GitHub features like pull requests and issue tracking to work together effectively.

## Instructions:

1. Form teams of 3-4 participants.
2. Create a new GitHub repository for your team's story.
3. Each team member should clone the repository to their local machine.
4. Create a new branch for each team member (e.g., alice-branch, bob-branch, carol-branch).
5. Each team member should write a part of the story in their respective branch and commit their changes.
6. Create pull requests to merge each team member's branch into the main branch.
7. Review and approve each other's pull requests, resolving any merge conflicts that arise.
8. Use GitHub issues to discuss plot ideas, character development, and any other aspects of the story.
9. Use Git commands like `git stash`, `git reflog`, and `git bisect` to manage your work and troubleshoot issues.
10. Create a final pull request to merge the main branch into a final-story branch.
11. Celebrate your collaborative story-writing success!

## Bonus Challenges:

- Use GitLens to view the history of your story and see who contributed each line.
- Create a GitHub Pages site to showcase your story to the world.
- Use Git hooks to automatically check for spelling errors before committing.

## Sample Solution:

### Team members clone the repository and create their branches:
```bash
git clone https://github.com/team/story.git
git branch alice-branch
git branch bob-branch
git branch carol-branch


Sample Solution:

Team members clone the repository and create their branches:

Copy codegit clone https://github.com/team/story.git
git branch alice-branch
git branch bob-branch
git branch carol-branch

Each team member writes their part of the story in their branch:

Copy codegit checkout alice-branch
echo "Once upon a time, in a land far away..." > story.txt
git add story.txt
git commit -m "Begin the story"

Team members create pull requests to merge their branches into main:

Copy codegit push -u origin alice-branch
Then, create a pull request on GitHub.

Team members review and approve each other's pull requests, resolving merge conflicts:

Copy codegit checkout main
git merge alice-branch
git merge bob-branch
Resolve any merge conflicts in story.txt.
Copy codegit add story.txt
git commit -m "Resolve merge conflict"

Use GitHub issues to discuss story ideas and track progress.
Use Git commands to manage work and troubleshoot issues:

Copy codegit stash
git reflog


Create a final pull request to merge main into final-story:

Copy codegit checkout -b final-story
git merge main
git push -u origin final-story
Then, create a pull request on GitHub.

Celebrate the successful completion of the story-writing hackathon!

This hackathon challenge covers various topics from the Git and GitHub tutorial, including branching, merging, pull requests, issue tracking, and troubleshooting. Participants will gain hands-on experience collaborating on a project using Git and GitHub.
