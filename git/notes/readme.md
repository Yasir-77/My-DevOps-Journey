## Introduction to Git

### Git content to study:

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

  




