# Development Guide

*Tips and tricks for writing software.*

## About the ChitambarLab Github Group

The ChitambarLab github group is a collaborative space to share and publish software. Our goal is to build software tools that support general quantum information research while providing computational transparency into our own research. This github group supports the research of Dr. Eric Chitambar's Lab at the University of Illinois Urbana-Champaign, [https://quantum-entangled.ece.illinois.edu/](https://quantum-entangled.ece.illinois.edu/).

## Git Flow

Git is used for version control in collaborative software development. A detailed git workflow is described at
[www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow).

### Branches

* `master` - The main branch for the codebase. This branch always contains working and complete code.
* `integration` - The branch where commits from different collaborators are merged together. This branch is a buffer between new code and the stable code in `master`. 
* `<feature>` - The branch where new code is developed.

### Cloning a repository

In order to run or make changes to code in a git repository, it must be downloaded locally. The `git clone` command handles this task.

1. Copy the repository to your local machine: `git clone <repository-clone-url>`
2. Navigate into the cloned project folder: `cd repository-dir`

### Get the latest code

1. Switch to the `integration` branch: `git checkout integration`
2. Get the most recent changes: `git pull origin integration`

### Develop a new feature

A feature:
* Performs a new task or modifies existing functionality.
* Can be completed within a few hours of work.
* Is tested sufficiently to ensure bug free operation and correctness of functionality.
* Is documented such that a collaborator can make sense of your work.

All new code should be developed in a feature branch named for the work it contains.

1. Create a new branch: `git checkout -b new-feature-name`
2. Write and test some code.
3. Add changes to to your branch: `git add new_file`
4. Commit changes to your branch: `git commit -m "short description of change"`
5. Push your changes to the local branch: `git push -u origin new-feature-name`

### Merge changes

When a feature is complete, it's code must be merged with the integration branch.

1. Pull the integration branch into your feature branch: `git pull --rebase origin integration`
    * Test your changes to make sure nothing is broken from integration.
    * Commit any changes from integration to your feature branch: `git push -u origin new-feature-name`
2. Checkout integration branch: `git checkout integration`
3. Merge feature branch with integration branch: `git merge new-feature-name`
4. Push merged commits to head of integration: `git push -u origin integration`

## Setup

### Python

Python is widely used programming language, install instructions are found at [www.python.org/downloads/](https://www.python.org/downloads/).

The official python documentation can be found at [https://docs.python.org/3/](https://docs.python.org/3/).

### Jupyter Notebook

Jupyter Notebook is a web-based IDE for writing python and julia code. Notebooks provide a nice environment to prototype or present code, however, they do not allow code to be modular or reusable *e.g.* use a notebook to help illustrate a technical argument, do not write code in a notebook which you would like to reuse at a later time. Reusable code should be written in packages.

For Jupyter Notebook install instructions, visit [https://jupyter.org/install.html](https://jupyter.org/install.html).

### Qiskit

For Qiskit install instructions, visit [https://qiskit.org/documentation/install.html](https://qiskit.org/documentation/install.html).

To run Qiskit on a quantum computer you will need to create an account at [https://quantum-computing.ibm.com/](https://quantum-computing.ibm.com/).

### Julia

Julia is a technical programming language, for Julia install instructions, visit [https://julialang.org/downloads/](https://julialang.org/downloads/).

For Julia documentation, visit [https://docs.julialang.org/en/v1/](https://docs.julialang.org/en/v1/)

