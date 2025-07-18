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

###
The fundamental difference between git pull and git fetch lies in how they interact with your local working directory and local branches.

Think of it as a two-step process:

Downloading new information (Fetch)

Integrating that information into your current work (Merge/Rebase)

git fetch does only step 1.
git pull does both step 1 and step 2.

Here's a detailed breakdown:

git fetch
git fetch is the "safe" way to get updates from a remote repository.

What it does:

Downloads commits, files, and refs (references like branches and tags) from the remote repository to your local Git repository. It updates your remote-tracking branches (e.g., origin/main, origin/feature-branch).

It DOES NOT merge or modify your local working directory or your currently checked-out local branches. Your local files remain untouched.

Analogy:
Imagine git fetch as checking the mail. You go to your mailbox (your local Git repository) and collect all the new mail (commits, changes) from the post office (remote repository). You can see what's new, read the envelopes, but you haven't opened any letters or integrated them into your daily life yet.

When to use git fetch:

To see what's new without affecting your current work: You want to know if there are changes on the remote, but you're in the middle of something and don't want to risk conflicts or interruptions.

To review changes before merging: After fetching, you can use git log origin/main (or the relevant remote-tracking branch) to see the new commits, or git diff main origin/main to see the differences between your local main and the remote's main before deciding to integrate them.

When working in a team: It's good practice to git fetch frequently to stay aware of others' progress without immediately merging their changes into your active branch.

Example:

Bash

git fetch origin
This will fetch all changes from the origin remote. After this, if you type git status, Git might tell you "Your branch is behind 'origin/main' by X commits." This tells you there are new changes available, but they haven't been applied to your local main branch yet.

git pull
git pull is a convenience command that automates the process of fetching and then integrating.

