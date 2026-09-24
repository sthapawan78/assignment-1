## Git Fundatamental
1. Git has three places a change can live: the working directory, the staging area, and the repository.Describe each, and explain what you would lose if the staging area did not exist.

- Working directory is where we do code, create file, edit them or delete files in our project.

- Staging area is the place where we select which changes are needed to be committed.

 - The Repository is the permanent snapshot of our project.

 2. git init and git clone both leave you with a Git repository. Explain what each one actually does, and give a situation where each is the right choice.

 - git init initializes the Git repository in our local folder

 - When we want to create some new project and want it to be tracked by git.

 - git clone is used to copy the git repository in our local folder.

 - When we want to work in some project which was already progressed by our teammate


 

 3. What does a commit store, and why is "committing" not the same as "saving a file"? Why is Git much less useful if user.name and user.email are unset or wrong?

 - A commit is the snapshot of staged changes in our git repository. Commit stores the snapshot of files and changes made in files. It also saves commit message and link it to the parent commit.

 - Saving a file stores the files in our local folder but git commit record our files and changes in file in git repository.

 - The user.name and user.email settings identify the author of a commit. If they are unset, Git may refuse to create commits, and if they are incorrect, commit authorship and GitHub attribution may be inaccurate.

 4. git status, git log, and git diff answer three different questions. State the question each one answers, and describe a moment in your workflow where you would reach for each.

 - git status shows the current state of the working directory and staging area, including modified,staged and untracked files. It is used before commiting  to check which files are changed.

 - git log shows the history of previous commits, messages. It is used to review the previous commits.

 - git diff displays the differences between the local file versions and git repo version. It is used before commiting to know what changes made.

 5. Explain what makes a commit message good. Why is "update" a genuine problem for a team six months later, and when is it worth writing a message body rather than just a summary line?

 - A good commit message clearly explains what changed and, when necessary, why it changed. It helps you and your teammates understand the project history later. A good commit message should be clear,specific, short and easy to understand.
 ''' git commit -m "git_theory.md is added"
 '''

 - A message like "update" is a problem because it provides no useful information about what was changed, making the project history difficult to understand months later.

 - For small changes, a summary line is usually enough. But a message body is useful when the change needs additional context, especially when the reason or consequences aren't obvious from the code.

## Remotes and the everyday workflow

6. Explain the relationship between your local repository and origin . What do push and pull each move, in which direction, and why is pulling before pushing the habit to build?

- My local repository is the Git repository on my computer, while origin is the remote repository, usually on GitHub.

- git push sends local commits to the git repository, while git pull brings the git repository changes in our local repository.

- I should pull before pushing because my teammates may have made changes. Pulling first helps me stay updated, avoid conflicts, and work smoothly as a team

7. git fetch and git pull are not the same command. What is the difference, and when would you deliberately choose fetch?

- git fetch downloads the latest changes from the remote repository but doesn't apply them to my current branch.

- git pull downloads the changes and merges them into my current branch.

- I would deliberately use git fetch when I want to check what my teammates have changed before merging it into my own work. This gives me more control and helps me avoid unexpected conflicts.

## Branching, merging, pull requests

8. A branch in Git is often described as "just a pointer." Explain what that means, and explain concretely what goes wrong on a team when everyone commits directly to main.

- A branch in Git is like a pointer that points to a specific commit. When I make a new commit, the branch pointer moves to that latest commit.

- If everyone commits directly to main, changes from different team members can overlap, causing merge conflicts and making it harder to review or test code. Using separate branches helps everyone work independently and merge their changes safely.

9. A merge conflict happens when two branches change the same lines of the same file. Explain why Git cannot resolve this automatically, what the <<<<<<< ======= , >>>>>>> markers mean, and what you must do to finish the merge.

A merge conflict happens when two branches change the same lines, and Git cannot decide which change to keep automatically.

The markers show the conflicting changes:

<<<<<<< → My branch's changes.

======= → Separates the two versions.

>>>>>>> → The other branch's changes.

To finish the merge, I must review the changes, choose or combine the correct ones, remove the markers, save the file, stage it, and commit the merge.

10. You could merge a branch locally with git merge and push. What does opening a Pull Request add that a local merge does not? What belongs in a PR description?

A local git merge combines the changes directly, but a Pull Request (PR) adds a place for teammates to review and discuss the changes before merging.

A PR description should briefly include:

- What was changed
- Why it was changed
- Any important notes or issues
- How it was tested

## Issues

11. Explain the purpose of labels and assignees on an Issue, and what Fixes #12 in a merged PR does. Why is linking work to Issues better than closing them by hand?

Labels help categorize an Issue, while assignees show who is responsible for working on it.

Fixes #12 in a PR links the PR to Issue #12 and automatically closes the Issue when the PR is merged.

Linking Issues is better because it keeps the work and its history connected, making it easier to track what was done and why.

## Project structure, environments, secrets

12. Why should .gitignore be one of your first commits? If a file is already tracked, does adding it to .gitignore stop Git from tracking it — and if not, what do you do instead?

- .gitignore should be added early so files like passwords, API keys, temporary files, and build files don’t accidentally get committed.

- If a file is already tracked, adding it to .gitignore won’t stop Git from tracking it. I need to remove it from tracking with:

git rm --cached filename

Then commit the change

13. Explain the difference between .env and .env.example, and why they get opposite treatment. If a real API key was committed three weeks ago, why is deleting it in a new commit not a fix, and what should actually be done?

- .env contains real secrets like API keys, so it should be kept private and added to .gitignore.

- .env.example contains only placeholder values, so it can be safely committed to show others what variables they need.

- If a real API key was committed three weeks ago, deleting it in a new commit doesn’t remove it from Git history. The key should be revoked/rotated immediately, then removed from the repository history if necessary.

14. What problem do a virtual environment and requirements.txt solve together?Why is never committed, when requirements.txt always is?

- A virtual environment keeps a project’s packages separate from the rest of my system, while requirements.txt lists the packages and versions needed to run the project.

- The virtual environment is never committed because it contains local files and can be recreated. requirements.txt is committed so others can install the same dependencies and run the project consistently.

15. Explain what venv/ itself git push --force does to a shared branch and whose work it can destroy. How does --force-with-lease behave differently, and why is that safer?

- If venv/ is committed, it pushes the whole virtual environment to GitHub, which is unnecessary and can cause problems.

- git push --force can overwrite the remote branch, potentially destroying other people's commits.

- git push --force-with-lease is safer because it checks whether the remote branch has changed before overwriting it. If someone else has pushed changes, Git stops the push instead of blindly replacing their work