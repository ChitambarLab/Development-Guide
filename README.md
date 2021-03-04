# Development Guide

*Tips and tricks for writing software.*

## About the ChitambarLab Github Group

The ChitambarLab github group is a collaborative space to share and publish software. Our goal is to build software tools that support general quantum information research while providing computational transparency into our own research. This github group supports the research of Dr. Eric Chitambar's Lab at the University of Illinois Urbana-Champaign, [https://quantum-entangled.ece.illinois.edu/](https://quantum-entangled.ece.illinois.edu/).

## Git Flow

Git provides version control for collaborative software development. Best practice git workflows are described at
[www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow).

Windows users may need to download git at [https://git-scm.com/download/win](https://git-scm.com/download/win).

### Branches

* `main` - The main branch for the codebase (note: older repositorys use `master`). This branch should always contain a working and complete version of the code.
* `<feature>` - The branch where new code is developed.

### Cloning a repository

To develop code in a git repository, you must download it locally. This task is handled by the `git clone` command.

1. Copy the repository to your local machine: `git clone <repository-clone-url>`
2. Navigate into the cloned project folder: `cd repository-dir`

### Get the latest code

1. Switch to the `main` branch: `git checkout main`
2. Get the most recent changes: `git pull origin main`

### Develop a new feature

New code is developed in a feature branch. The changes in the feature branch are independent from those in `main`.

1. Create a new branch: `git checkout -b new-feature-name`
2. Write and test some code.
3. Add changes to to your branch: `git add new_file`
4. Commit changes to your branch: `git commit -m "short description of change"`
5. Push your changes to the local branch: `git push -u origin new-feature-name`

### Merge changes

When a feature is complete, it's code must be merged into the `main` branch.
This is done by creating a *pull request* through the github UI.

A pull request enables:
* Collaborators to review your changes.
* Automated tests to be run before merging.

To preserve a working and maintainable codebase in the `main` branch, it is important that any merged changes satisfy the following requirements:
* Performs a new task or modifies existing functionality.
* Includes tests that ensure bug free operation and correctness of functionality.
* Includes documenation such that a collaborator can make sense of your work.

## Setup


### Julia

Julia is a technical programming language, for Julia install instructions, visit [https://julialang.org/downloads/](https://julialang.org/downloads/).

For Julia documentation, visit [https://docs.julialang.org/en/v1/](https://docs.julialang.org/en/v1/)

### Jupyter Notebook

Jupyter Notebook is a web-based IDE for writing python and julia code. Notebooks provide a nice environment to prototype or present code, however, they do not allow code to be modular or reusable *e.g.* use a notebook to help illustrate a technical argument, do not write code in a notebook which you would like to reuse at a later time. Reusable code should be written in packages.

For Jupyter Notebook install instructions, visit [https://jupyter.org/install.html](https://jupyter.org/install.html).

### Python

Python is widely used programming language, install instructions are found at [www.python.org/downloads/](https://www.python.org/downloads/).

The official python documentation can be found at [https://docs.python.org/3/](https://docs.python.org/3/).

### Qiskit

For Qiskit install instructions, visit [https://qiskit.org/documentation/install.html](https://qiskit.org/documentation/install.html).

To run Qiskit on a quantum computer you will need to create an account at [https://quantum-computing.ibm.com/](https://quantum-computing.ibm.com/).

## Julia Development

### Workflow

1. Clone the git repository and create a feature branch off of integration.
2. Open the julia REPL and enter Pkg mode by typing `]`. Then run `develop --local .` to build to module from your local files.
3. Write a function in the `./src` directory and a test in the `./test` directory.
4. Run the test:
      * In Pkg mode, type `test PackageName` to run all tests for the package.
      * Equivalently, run all tests with `julia test/runtests.jl` or, a single test with `julia test/path/to/test.jl`
5. Document the new functionality:
      * Follow the adding documentation instructions for [Documenter.jl](https://juliadocs.github.io/Documenter.jl/stable/man/guide/#Adding-Some-Docstrings-1).
      * Build the local documentation `julia docs/make.jl`
      * Host the docs webpage. First navigate to the `./docs/build/` directory, then run `python3 -m http.server --bind localhost`
6. When finished with development, push your completed changes to your feature branch and merge into integration.


### Writing Code

An Integrated Development Environment (IDE) can help streamline the development process. How you write code is a matter of personal preference, but two great open-source text editors specialized for julia are
* [VS Code](https://www.julia-vscode.org/)
* [Atom](https://junolab.org/)


### Automated Testing

Tests make sure that your code works properly during and after development. Tests should be developed simultaneously. with your code. Software should not be considered complete if it is not tested. [Test-Driven Development](http://agiledata.org/essays/tdd.html) is a widely used practice in industry.

Tests are stored in the `./test` directory. For more information about testing, please refer to the [Julia Test docs](https://docs.julialang.org/en/v1/stdlib/Test/).

### Documentation

The world will see your documentation so make sure it's professional, concise, and useful. Julia documentation is buit with [Documenter.jl](https://juliadocs.github.io/Documenter.jl/stable/). 

