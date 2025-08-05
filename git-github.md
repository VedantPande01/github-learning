# Git & GitHub Notes

This repository contains my personal notes on **Git** and **GitHub** as I learn version control and collaboration tools.

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

## 📌 Summary

- Git is a local version control tool.
- GitHub is an online platform for hosting Git repositories.
- Proper configuration is essential before using Git.
- You can work with multiple GitHub accounts using global and local configurations.

---

Happy coding! 🚀
