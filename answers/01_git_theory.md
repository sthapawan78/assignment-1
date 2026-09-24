## Git Fundatamental
1. Git has three places a change can live: the working directory, the staging area, and the repository.Describe each, and explain what you would lose if the staging area did not exist.

Working directory is where we do code, create file, edit them or delete files in our project.

Staging area is the place where we select which changes are needed to be committed.

 The Repository is the permanent snapshot of our project.

 2. git init and git clone both leave you with a Git repository. Explain what each one actually does, and give a situation where each is the right choice.

 git init initializes the Git repository in our local folder

 When we want to create some new project and want it to be tracked by git.

 git clone is used to copy the git repository in our local folder.

 When we want to work in some project which was already progressed by our teammate


 

 3. What does a commit store, and why is "committing" not the same as "saving a file"? Why is Git much less useful if user.name and user.email are unset or wrong?

 - A commit is the snapshot of staged changes in our git repository. Commit stores the snapshot of files and changes made in files. It also saves commit message and link it to the parent commit.

 - Saving a file stores the files in our local folder but git commit record our files and changes in file in git repository.

 - The user.name and user.email settings identify the author of a commit. If they are unset, Git may refuse to create commits, and if they are incorrect, commit authorship and GitHub attribution may be inaccurate.