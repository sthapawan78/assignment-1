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
 