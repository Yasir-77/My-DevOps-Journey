# Introduction to Git

## Git content to study:

- Why is Git important
- Getting started on Git
- Linking local and remote repository
- Demo
- Commits
- Branching
- Pull requests
- Editing changes into Git
- Git ignore

### What is git?

Git is a distributed version control system that enables users to collaborate on projects, tracking changes in files and directories while providing a history of snapshots and the ability to manage different branches and merge code changes efficiently

### Why is Git essential in modern software development

- Industry standard - It is a fundamental skill and is listed as an essential skill in many tech roles. Git enables developers to work more effieciently and collaborate effectively with their team. Used by many organisations and is wide spread, easy integration. Gits verstaility make it suitable for projects of all sizes and complexities.

- Version control - Git allows developers to track changes made to files over time, keeping a history of all modifications. This makes it easy to revert to previous versions if something goes wrong or to see how the code evolved.
  
- Backup and restore - Git naturally serves as a backup mechanism since every clone of a repository contains the entire project history. If a server crashes, the project can be fully recovered from any developer’s local copy. This prevents accidental data loss and prevents any unintended changes. Allowing the code to revert back to stable state.

- Branching and merging -  Git’s branching model lets developers create isolated branches for new features, bug fixes, or experiments. This isolates the work, reducing the risk of bugs or instability in the main codebase. Once the changes are ready, they can be merged into the main project. Allows developers to work on multiple aspects of the same project.

- How to Create a Git Repository & link it locally.

To congirgure Git and link it to any terminal type:

git config --global user.name "(username)"

git config --global user.email "(email address)"

Then clone the repository by pressing the code button and copying the html. Then type git clone (url)
```
git config --global user.name "username"
```
```
git config --global user.name "email"
```
```
git clone url
```

### Importance of README file (README.md)

- Project Title - The README.md provides a summary of the project, including its purpose, goals, and functionality. It helps users and contributors understand what the project is about without needing to dig through the code.

- Description - The README.md may outline how contributors can help, including contribution guidelines, coding standards, and how to report bugs or submit feature requests. This makes the project more open and collaborative, especially for open-source repositories.

- Installation instructions - The README.md typically lists any dependencies or prerequisites required to run the project, such as libraries or tools, and provides step-by-step installation instructions. This ensures users can set up the project environment correctly.

- Contribution Workflow - It may describe the directory structure of the repository and provide instructions on how to set up a development environment or contribute via pull requests. This simplifies the onboarding process for new developers.

## Understanding commits

### What is the purpose of commits:

Git allows you to create a snapshots of your project at specific points and time this helps isolate and document changes or additions making project management easier.

Every committing git records what changes were made when and by who this detailed tracking is essential for maintaining a clear project history

Using commit messages you can describe the changes made and the reasons behind them this practice helps everyone understand the context and purpose of each change.

Git also supports team collaboration by providing a comprehensive history of all changes, the Audit trail it creates is invaluable for understanding the evolution of the project and reviewing decisions

Git enables efficient version control by tracking every change to the code base, you can manage different versions to your project and revert previous versions if needed. 

The detailed audit trail and git allows you to review the history of changes and understand why they were made this transparency is crucial for team collaboration and project management.

Committing git record changes in detail ensuring that every modification is tracked and documented this detailed record helps in maintaining a robust project history.

Git also allows you to trouble shoot easier by allowing you to revert to a previous state and isolate problematic changes if anything goes wrong you can quickly identify and fix issues by reviewing the commit history.

### Good commit practises:

- Commit often
- Write clear commit messages
- Use command style in messages
- Comit related changes together
- Test before committing
- Avoid committing generated files
- Break down large changes
- Use consistent message stle
- Include references

## Branching 

### Why is Branching a good thing?

Branching allows developers to work on different features, fixes, or experiments without affecting the main codebase.

Branching allows multiple developers to work on the same project simultaneously. Each team member can create their own branch for the feature or bug they are working on.

By keeping new work in branches, teams can review code before merging it into the main branch.

Branches can be used for different versions of software. For example, you might have a stable branch for production, a development branch for upcoming feature

When an urgent bug fix is needed, developers can create a fix branch, make the necessary changes, and merge it into the main branch without interfering with ongoing feature development.

### Git flow workflow

#### Key Branches:

Main (or master): Represents the production-ready code.

Develop: Reflects the latest development state and is where features are merged once completed and tested.

Feature branches: For working on new features or tasks.

Release branches: Created when preparing a new release to make final changes and test it before merging into the main branch.

Hotfix branches: For urgent bug fixes in production.

#### Workflow:

Developers create feature branches from develop, complete the feature, and merge them back into develop.

A release branch is created when a set of features is ready for production. After testing and polishing, it gets merged into both main and develop.

For urgent fixes, a hotfix branch is created from main and merged back into both main and develop.

![image](https://github.com/user-attachments/assets/e66f4c0e-b6df-4e90-a0d1-f95c5e413ae2)

## Pull requests

### Purpose of Pull requests

- Review code before integrating
- Keeps a record
- Maintain a high quality of code
- Assign Team members to review pull requests













  




