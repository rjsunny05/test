![image](https://i.ytimg.com/vi/ptK9-CNms98/maxresdefault.jpg)




| Author          | Created on | Version   | Last updated by | Last edited on | Internal Reviewer | L0     | L1      | L2     |
|-----------------|------------|-----------|------------------|----------------|--------------------|--------|---------|--------|
| Rajeev Ranjan | 17-04-25   | version 1 | N/A              | N/A            | Priyanshu          | Khushi | Mukul | Piyush |


## Table of Contents
1. [Introduction](#introduction)
2. [Key Concept](#key-concept)
     1. [Repositories](#repositories)
     2. [Branches](#branches)
     3. [Pull Request](#pull-requests)
3. [Issues](#issues)
4. [GitHub Actions](#github-actions)
5. [gitignore](#gitignore)
6. [Collaboration Tools](#collaboration-tools)
7. [Conclusion](#conclusion)
8. [Contacts Information](#contacts-information)
9. [References](#references)

# GitHub Documentation

# Introduction
GitHub is a web-based platform for version control and collaboration, allowing multiple developers to work on projects simultaneously. It is built around Git, a distributed version control system, and is widely used for hosting open-source and private code repositories.

---

# Key Concept

##  Repositories
A **repository (repo)** is the fundamental unit in GitHub. It contains all the project files and the entire revision history. Repositories can be public or private, and users can **clone**, **fork**, or **contribute** to them.

- **Clone**: Copies the repository to your local system.
- **Fork**: Makes a copy under your account to experiment or contribute.
- **README**: A default documentation file often used to describe the project.

##  Branches
**Branches** allow you to diverge from the main codebase to work on new features or fixes without affecting the main project (usually `main` or `master` branch).

- Common use: Feature development, bug fixes.
- **Default branch** is usually the main production code.
- You can merge branches back into the main branch after changes are tested.
![image](https://d8it4huxumps7.cloudfront.net/uploads/images/6536475adca0a_git_create_branch_01.jpg?d=2000x2000)

- **Main Branch**:
The default branch where the final, stable version of the code resides.

- **Feature Branches**:
Branches are created from the main branch to work on specific features, bug fixes, or tasks without impacting the main codebase.

##  Pull Requests
A **Pull Request (PR)** is a request to merge code from one branch into another, typically reviewed by collaborators.

- Includes **code review**, **comments**, and **approval workflows**.
- Can trigger automated tests or workflows (via GitHub Actions).
- Promotes peer review and ensures code quality.

---

#  Issues
GitHub **Issues** are used to track bugs, feature requests, tasks, and improvements.

- Users can label, assign, and prioritize issues.
- Can be linked to commits and pull requests.
- Supports templates for consistency.
- Supports closing issues via commit messages (`Fixes #123`).

---

#  GitHub Actions
**GitHub Actions** is GitHub’s built-in CI/CD tool that helps automate workflows.

- Automates tests, deployments, and code linting.
- Uses YAML files stored in `.github/workflows/`.
- Supports custom actions and marketplace integrations.
- Triggered on push, pull requests, or scheduled times.
![Screenshot 2024-11-21 130820](https://github.com/user-attachments/assets/225b811c-fd99-478a-b15e-b93474aff022)

---

#  .gitignore
The `.gitignore` file tells Git which files/folders to ignore in version control.

- Common for excluding compiled code, temporary files, secrets.
- Each language/project has standard `.gitignore` templates.
- Prevents sensitive or unnecessary files from being tracked.

Example:

node_modules/
.env
*.log

#  Collaboration Tools
GitHub provides several tools to support team collaboration:

- **Code Review**: In-line comments on pull requests.
- **Project Boards**: Kanban-style boards for task tracking.
- **Wikis**: For project documentation.
- **Discussions**: Community Q&A within repositories.
- **Notifications**: Email and in-app alerts for updates and mentions.
- **Teams & Permissions**: Granular access control for organizations.

---

#  Conclusion
GitHub is a comprehensive platform for code versioning, project management, and team collaboration. It empowers developers to work efficiently, automate processes, and maintain code quality. Its features like pull requests, issues, and GitHub Actions make it suitable for individual projects as well as enterprise-level development.








## Contacts Information
| Name         | Email address          |
|--------------|------------------------|
| Rajeev Ranjan          |     rajeevsunny05@gmail.com |

## References
| Links                                             | Descriptions                                                    |
|---------------------------------------------------|-----------------------------------------------------------------|
| https://www.simplilearn.com/tutorials/git-tutorial/what-is-github | Document format followed from this link                         |


