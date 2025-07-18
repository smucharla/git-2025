This project is setup to learn, refresh and practice git commands, clone, pull, push to online repositories.

The command git push --set-upstream origin main performs a git push operation with a specific configuration that links your local main branch to the main branch on the origin remote.

Let's break down each part:

git push: This is the fundamental Git command used to upload your local commits to a remote repository.

--set-upstream: This is the key part of the command, often abbreviated as -u. It tells Git to do two things in addition to the standard push:

Establish a Tracking Relationship: It sets up a "tracking relationship" between your current local branch (in this case, main) and the specified remote branch (origin/main).

Configure Future Pushes/Pulls: Once this tracking relationship is established, you can simply type git push or git pull (without specifying the remote and branch names) in your local main branch, and Git will automatically know to push to or pull from origin/main.

origin: This is the default name given to the remote repository from which you typically cloned your project (or where you intend to push your code if you started locally). It refers to the URL of your GitHub repository (or GitLab, Bitbucket, etc.).

main: This is the name of the branch you are pushing. In this context, it refers to your local main branch.

###
Conencting to github via SSH

1. generate ssh-keys using ssh-keygen command
2. Copy the contents of ~/.ssh/id_ed25519.pub into Mac's clipboard
3. Goto github. Profile-->settings-->Add SSh keys under access -->add ssh_key --> Give it a name and copy the contents.
4. execute git remote -v
5. Remove the old https remote using "git remote remove origin"
6. Add the SSH remote usingthe below command.
   git remote add origin git@github.com:smucharla/git-2025.git



