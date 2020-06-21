# Development Guide

*Tips and tricks for writing software.*

## Git Flow

Best practices for git workflows are described at
[www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow).

The following workflow outlines a best practice git workflow. Simplifications of this workflow may make sense depending on the project and number of collaborators.

### Branches

* `master` - The main branch for the codebase. This branch should always contain working and complete code.
* `integration` - The branch where commits from different collaborators are merged together. This branch 
* `<feature>` - The branch where new code is developed. A new branch is created for each set of features


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
4. Merge feature branch with integration branch: `git merge new-branch-name`
5. Push merged commits to head of integration: `git push -u origin integration`


## Setup

### Python

For python install instructions, visit [www.python.org/downloads/](https://www.python.org/downloads/).

### Jupyter Notebook

For Jupyter Notebook install instructions, visit [https://jupyter.org/install.html](https://jupyter.org/install.html).

### Qiskit

For Qiskit install instructions, visit [https://qiskit.org/documentation/install.html](https://qiskit.org/documentation/install.html).

To run Qiskit on a quantum computer you will need to create an account at [https://quantum-computing.ibm.com/](https://quantum-computing.ibm.com/).

### Julia

Julia is a high-performance technical programming language. It could be described as the intersection of python, matlab, and C++.

For Julia install instructions, visit [https://julialang.org/downloads/](https://julialang.org/downloads/).

For Julia documentation, visit [https://docs.julialang.org/en/v1/](https://docs.julialang.org/en/v1/)

