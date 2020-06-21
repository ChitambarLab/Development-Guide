# Development Guide

*Tips and tricks for writing software.*

## About the ChitambarLab Github Group

The ChitambarLab group is a collaborative space to share and publish software. Our goal is to build software tools that support general quantum information research while providing computational transparency into our own research.

This github group supports the research of Dr. Eric Chitambar's Lab at the University of Illinois Urbana-Champaign, [https://quantum-entangled.ece.illinois.edu/](https://quantum-entangled.ece.illinois.edu/).


## Git Flow

Git is used for version control in collaborative software development.

Best practices for git workflows are described at
[www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow).

The following workflow outlines a best practice git workflow. Depending on the project and number of collaborators, this workflow can be simplified.

### Branches

* `master` - The main branch for the codebase. This branch should always contain working and complete code.
* `integration` - The branch where commits from different collaborators are merged together. The main purpose of the integration branch is serve as a buffer between new code and the stable code in `master`. The `integration` branch contains the most up-to-date codebase because it contains all changes which have not yet merged with `master`. 
* `<feature>` - The branch where new code is developed. A feature branch is always created from the `integration` branch. Independent features should be developed in separate feature branches. 

### Get the latest code

1. Switch to the `integration` branch: `git checkout integration`
2. Get the most recent changes: `git pull origin integration`

### Develop a new feature

1. Create a new branch: `git checkout -b new-branch-name`
2. Write and test some code.
3. Add changes to to your branch: `git add new_file`
4. Commit changes to your branch: `git commit -m "short description of change"


### Merge changes

When a feature is complete, it's code must be merged with the integration branch.

1. Pull the `integration` branch into your feature branch: `git pull --rebase origin integration`
2. Test your changes to make sure you don't break integration.
3. Checkout `integration` branch: `git checkout integration`
4. Merge feature branch with `integration` branch: `git merge new-branch-name`
5. Push merged commits to head of `integration`: `git push -u origin integration`

## Setup

### Python

Python is widely used programming language. 

For python install instructions, visit [www.python.org/downloads/](https://www.python.org/downloads/).

The official python documentation can be found at [https://docs.python.org/3/](https://docs.python.org/3/).

### Jupyter Notebook

Jupyter Notebook is a web-based IDE for writing python and julia code. Notebooks provide a nice environment to prototype or present code, however, they do not allow code to be modular or reusable *e.g.* use a notebook to help illustrate a technical argument, do not write code in a notebook which you would like to reuse at a later time. Reusable code should be written in packages.

For Jupyter Notebook install instructions, visit [https://jupyter.org/install.html](https://jupyter.org/install.html).

### Qiskit

For Qiskit install instructions, visit [https://qiskit.org/documentation/install.html](https://qiskit.org/documentation/install.html).

To run Qiskit on a quantum computer you will need to create an account at [https://quantum-computing.ibm.com/](https://quantum-computing.ibm.com/).

### Julia

Julia is a high-performance technical programming language.

For Julia install instructions, visit [https://julialang.org/downloads/](https://julialang.org/downloads/).

For Julia documentation, visit [https://docs.julialang.org/en/v1/](https://docs.julialang.org/en/v1/)

