# Git
[Git Official Website](https://git-scm.com/)

From the website: 
> Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.

Bellow is a list of most used git commands, but you can check the full [Git Documentation](https://git-scm.com/doc) for more information.

_Definitions of this file_: 
- params surrounded by `{}` are placeholders to be replaced with desired values.
- params surrounded by `[]` are optional and can be omitted.

## Repository Initialization

[`git init`](https://git-scm.com/docs/git-init): initializes a repository in the current directory. Git creates a `.git` folder inside the current directory to store all versioning and meta information of the repository.

[`git clone {repository_url} [{directory_name}]`](https://git-scm.com/docs/git-clone): creates a directory named `{directory_name}` and copies the repository found in the provided `{repository_url}` into the directory , adding a remote `origin` that points to the same URL used to clone the repository. If the param `{directory_name}` is not provided, git will use the repository name as the `{directory_name}`.

## Git Credentials

To configure a git repository to accept commits, it's required to provide a `username` and `password` of the current author. 

_For more information, check the [full `git config` docs](https://git-scm.com/docs/git-config)_.

`git config [--global] user.email {email}`: set the `user.email` of the current user. It could be any valid email address.

`git config [--global] user.name {name}`: set the `user.name` of the curren user. Use double quotes if the name has white spaces, e.g.: "Jo

_NOTE_: if the `--global` param is provided, the same email and name are going to be used for every commit created by the current OS user.

## Commits

From a repository directory, add all files to include in the commit:

[`git add [--all] [{file_path}]`](https://git-scm.com/docs/git-add): includes files to be included in the next commit. `--all` will add all modified files, but it's possible to specify a `{file_path}` to only include specific files. This command changes the file status.

[`git status`](https://git-scm.com/docs/git-status): displays the status of files that are present in the repository folder and differ from the their snapshot of the most recent commit.

[`git commit`](https://git-scm.com/docs/git-commit): creates a commit in the current branch that includes all staged files previously added by `git add`.

[`git log`](https://git-scm.com/docs/git-log): displays a summary of all commits on the current branch in historical order.

## Branches

Branches are separate versions of a project development timeline. They allow alternate versions of the files to co-exist in the same repository, branching from the same starting point. 

The working directory can only have one active branch at a time. Every commit will be done in the currently active branch.

When a repository is initialized, a single default `main` branch is created as active. 

[`git branch`](https://git-scm.com/docs/git-branch): lists all branches of the current repository

`git branch {branch_name}`: creates a new branch named `{branch_name}`.

`git checkout {branch_name}`: changes the current branch to the provided `{branch_name}`. If there are modified files, git will try to carry these files to the checked out branch. Since this operation could generate conflicts, it's advised to make sure the current branch doesn't have any uncommitted file.

## Remotes

[`git remote`](https://git-scm.com/docs/git-remote): lists all remote tracked repositories available on the current repository.

[`git push [{remote_alias}] [{remote_branch}]`](https://git-scm.com/docs/git-push): sends all updates on the current repository to the remote repository `{remote_alias}` to the `{remote_branch}`.

[`git pull [{remote_alias}] [{remote_branch}]`](https://git-scm.com/docs/git-pull): fetches all updates from the remote repository `{remote_alias}` of its `{remote_branch}` and applies to the currently active local branch.
