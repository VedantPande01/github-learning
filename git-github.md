# Git & GitHub Notes

This repository contains my personal notes on Git and GitHub, along with basic version control concepts and terminology.

## 🧠 Understanding Git and GitHub

- **Git** is a **Version Control System (VCS)** used to track changes in code. It allows you to **add**, **commit**, **push**, and perform many other actions to manage your project history.
- **GitHub** is a **web-based hosting platform** that lets you store your Git repositories online. It enables **collaboration**, **remote backups**, and **code sharing**.

> 🔹 In simple terms:  
> **Git** manages code changes locally.  
> **GitHub** stores that code remotely so others can access it.

## ⚙️ Installing Git

To check if Git is installed on your system, run:

```bash
git --version
```

If installed correctly, it will return the version number of Git.

## 🔧 Configuring Git

Before using Git, it's important to configure your identity:

### Global Configuration (applies to all repositories):

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

### Local Configuration (applies only to the current repository):

```bash
git config user.name "Your Name"
git config user.email "your-email@example.com"
```

> Use **global** if you're using the same GitHub account across all projects.  
> Use **local** if you're using a different GitHub account for a specific project.

## ✅ Checking Your Git Configuration

To verify your current Git configuration:

```bash
git config --list
```

This will display a list of all configured settings.

## Repository

A repository is a collection of files and directories that are stored together. It is a way to store and manage your code. A repository is like a folder on your computer, but it is more than just a folder. It can contain other files, folders, and even other repositories. You can think of a repository as a container that holds all your code.

There's a difference between simply having Git installed and actually tracking a specific folder with it. At any point you can run the following command to see the current state of your repository:

```bash
 git status
```

![Git Status](https://docs.chaicode.com/_astro/repo-status.JIM1nCWI_Z205yrX.webp)

Not all folders are meant to be tracked by git. Here we can see that all green folders are projects are getting tracked by git but red ones are not.

## Creating a repository (a.k.a Repo)

Creating a repository is a process of creating a new folder on your system and initializing it as a git repository. It’s just regular folder to code your project, you are just asking git to track it. To create a repository, you can use the following command:

```bash
git status
git init
```

`git status` command will show you the current state of your repository. `git init` initializes your current folder as a Git repository by adding a hidden `.git` folder. This adds a hidden .git folder to your project.

## Complete git flow

A complete git flow, along with pushing the code to github looks like this:

![Git Workflow](https://docs.chaicode.com/_astro/complete-flow.DYr-Pvsp_1IQISm.webp)

When you want to track a new folder, you first use init command to create a new repository. Then you can use add command to add the folder to the repository. After that you can use commit command to save the changes. Finally you can use push command to push the changes to github. Of course there is more to it but this is the basic flow.

## Stage

Stage is a way to tell git to track a particular file or folder. You can use the following command to stage a file:

```bash
git init
git add <file> <file2>
git status
```

Here we are initializing the repository and adding a file to the repository. Then we can see that the file is now being tracked by git. Currently our files are in staging area, this means that we have not yet committed the changes but are ready to be committed.

## Commit

A commit is a way to save changes to your repository. It is a way to record your changes and make them permanent. You can think of a commit as a snapshot of your code at a particular point in time. When you commit your changes, you are telling git to save them in a permanent way. This way, you can always go back to that point in time and see what you changed.

Usual flow looks like this:

![Commit Workflow](https://docs.chaicode.com/_astro/flow.DIk3TV2p_Zs00Un.webp)

```bash
git commit -m "commit message"
git status
```

Here we are committing the changes to the repository. We can see that the changes are now committed to the repository. The -m flag is used to add a message to the commit. This message is a short description of the changes that were made. You can use this message to remember what the changes were. Missing the -m flag will result in an action that opens your default settings editor, which is usually VIM. We will change this to vscode in the next section.

## Logs

```bash
git log
```

This command will show you the history of your repository. It will show you all the commits that were made to the repository. You can use the --oneline flag to show only the commit message. This will make the output more compact and easier to read.

```bash
git log --oneline
```

☕️ - Check git log docs

> Atomic commits are a way to make sure that each commit is a self-contained unit of work. This means that if one commit fails, you can always go back to a previous commit and fix the issue. This is important for maintaining a clean and organized history in your repository.

## gitignore

Gitignore is a file that tells git which files and folders to ignore. It is a way to prevent git from tracking certain files or folders. You can create a gitignore file and add list of files and folders to ignore by using the following command:

Example:

```bash
# .gitignore file

node_modules/
.env
.vscode/

```

Now, when you run the `git status` command, it will not show the `node_modules` and `.vscode` folders as being tracked by git.
<br>

## 📌 Conclusion

- Git is a local version control tool.
- GitHub is an online platform for hosting Git repositories.
- Proper configuration is essential before using Git.
- You can work with multiple GitHub accounts using global and local configurations.
- In this section, we have learned about the basics of git and how to use it to track changes to your files and folders. We have also learned about the different commands that you can use to interact with your repository, such as init, add, commit, log, etc

---

<br>
<br>
<br>

# Branches in Git.

Branches are a way to work on different versions of a project at the same time. They allow you to create a separate line of development that can be worked on independently of the main branch. This can be useful when you want to make changes to a project without affecting the main branch or when you want to work on a new feature or bug fix.

![branches work flow](https://docs.chaicode.com/_astro/branches.YOIsOP4X_Z2gjmSk.webp)

Some developers can work on Header, some can work on Footer, some can work on Content, and some can work on Layout. This is a good example of how branches can be used in git.

## HEAD in git

The HEAD is a pointer to the current branch that you are working on. It points to the latest commit in the current branch. When you create a new branch, it is automatically set as the HEAD of that branch.

> the default branch used to be master, but it is now called main. There is nothing special about main, it is just a convention.

## Creating a new branch

To create a new branch, you can use the following command:

```bash
git branch
git branch bug-fix
git switch bug-fix
git log
git switch main
git switch -c dark-mode
git checkout orange-mode

```

Some points to note:

`git branch` - This command lists all the branches in the current repository.

`git branch bug-fix` - This command creates a new branch called bug-fix.

`git switch bug-fix` - This command switches to the bug-fix branch.

`git log` - This command shows the commit history for the current branch.

`git switch main` - This command switches to the main branch.

`git switch -c dark-mode` - This command creates a new branch called dark-mode. the -c flag is used to create a new branch.

`git checkout orange-mode` - This command switches to the orange-mode branch.

> Commit before switching to a branch<br>
> Go to .git folder and checkout to the HEAD file

<br>
<br>
<br>

## Merging branches

Merging is about bringing changes from one branch to another.

    In Git we have two types of merges :

        1. Fast-Forward Merges (If branches have not diverged).
        2. 3-Way Merges (if branches have diverged).

### Fast-forward merge

This one is easy as branch that you are trying to merge is usually ahead and there are no conflicts.

When you are done working on a branch, you can merge it back into the main branch. This is done using the following command:

```bash
git checkout main
git merge bug-fix
```

![Merging Branch](https://docs.chaicode.com/_astro/fast-forward-merge.2JLs9oN__176LJB.webp)

<br>
<br>
<br>

Some points to note:

1. `git checkout main` - This command switches to the `main` branch.
2. `git merge bug-fix` - This command merges the `bug-fix` branch into the `main` branch.

This is a fast-forward merge. It means that the commits in the `bug-fix` branch are directly merged into the `main` branch. This can be useful when you want to merge a branch that has already been pushed to the remote repository.
<br>

### 3 Way merge

![Git Workflow](https://docs.chaicode.com/_astro/three-way-merge.C3EirtdW_Z1P6LdI.webp)
<br>

In this type of merge, the main branch has additional commits that are not present in the `bug-fix` branch. This is not a fast-forward merge. Here git looks at 3 different commits [common ancestor of branches + tips of each branch] and combines the changes into one merge commit.

When you are done working on a branch, you can merge it back into the main branch. This is done using the following command:
<br>

```bash
git checkout main
git merge bug-fix
```

<br>
If the command are same, what is the difference between fast-forward and not fast-forward merge?

<br>

The difference is resolving the conflicts. In a fast-forward merge, there are no conflicts. But in a not fast-forward merge, there are conflicts, and there are no shortcuts to resolve them. You have to manually resolve the conflicts. Decide, what to keep and what to discard. VSCode has a built-in merge tool that can help you resolve the conflicts.

<br>

![Git Workflow](https://docs.chaicode.com/_astro/merge-conflict.DXsrSRd3_Z6K0BV.webp)
<br>

## Managing conflicts

There is no magic button to resolve conflicts. You have to manually resolve the conflicts. Decide, what to keep and what to discard. VSCode has a built-in merge tool that can help you resolve the conflicts. I personally use VSCode merge tool. Github also has a merge tool that can help you resolve the conflicts but most of the time I handle them in VSCode and it gives me all the options to resolve the conflicts.

Overall it sounds scary to beginners but it is not, it’s all about communication and understanding the code situation with your team members.

### Rename a branch

You can rename a branch using the following command:

```bash
git branch -m <old-branch-name> <new-branch-name>
```

### Delete a branch

You can delete a branch using the following command:

```bash
git branch -d <branch-name>
```

### Checkout a branch

You can checkout a branch using the following command:

```bash
git checkout <branch-name>
```

### List all branches

You can list all branches using the following command:

```bash
git branch
```

List all branches means that you are going to see all the branches in your repository.

## 📌 Conclusion

In this section, we have learned about the different types of merges and how to resolve conflicts. We have also learned about the importance of branching and merging in Git and Github.
