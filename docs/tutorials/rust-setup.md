# Setting up a dev container for Rust

* Primary author: [Yohan Choi](https://github.com/YummyYohan)

* Reviewer: Nabiha Choudhury

## Prerequisites:

1. **GitHub account:** If you dont have a GitHub account, sign up at [GitHub](https://github.com/signup).

2. **Git installed:** Make sure to install [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) if you haven't already.

3. **Visual Studio Code** (VS Code): Downloads code [here](https://code.visualstudio.com/)

# Part 1. Project Setup: Creating the Repository

## Step 1. Create a Local Directory and Initialize Git

(A) Open up your terminal or command prompt.

(B) Create a new directory

    mkdir rust-tutorial
    cd rust-tutorial

(C) Initialize a new Git repository:

    git init

(D) Create a README file:

    
    echo "# Rust Tutorial" > README.md
    git add README.md
    git commit -m "Initial commit with README"

## Step 2. Create a Remote Repository on GitHub


(1) Log in to your GitHub and go to [Create a New Repository](https://github.com/new) page.

(2) Fill in the following details:

- Repository Name: rust-tutorial
- Desscription: "Tutorial for setting up a basic project for Rust programming language
- Visibility: Public

!!! warning
    For this tutorial, do not initialize the repository with a README, .gitignore, or license.

(3) <strong>Create Repository</strong>

## Step 3. Linking your Local Repository to GitHub

(1) Add the GitHub repository as a remote by:

    git remote add origin https://github.com/<your-username>/comp423-course-notes.git

Replace `<your-username>` with your GitHub username.

(2) Check your default branch name with the subcommand `git branch`. If the branch is not starred `main`, rename it to `main` with the following command: `git branch -M main`.

!!! info

    Old versions of `git` choose the name `master` for the primary branch, but these days `main` is the standard primary branch name.

(3) Push your local commits to the GitHub repository:

    git push --set-upstream origin main

(4) In your web browser, refresh your GitHub repository and check that the same commit you made locally has now been <em>pushed</em> to remote. You can also use the `git log` locally to see the commit ID and message and check if the ID matches with the most recent commit on GitHub.
