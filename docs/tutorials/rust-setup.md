# Setting up a dev container for Rust

* Primary author: [Yohan Choi](https://github.com/YummyYohan)

* Reviewer: [Nabiha Choudhury](https://github.com/chnabi)

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

    git remote add origin https://github.com/<your-username>/rust-tutorial.git

Replace `<your-username>` with your GitHub username.

(2) Check your default branch name with the subcommand `git branch`. If the branch is not starred `main`, rename it to `main` with the following command: `git branch -M main`.

!!! info

    Old versions of `git` choose the name `master` for the primary branch, but these days `main` is the standard primary branch name.

(3) Push your local commits to the GitHub repository:

    git push --set-upstream origin main

(4) In your web browser, refresh your GitHub repository and check that the same commit you made locally has now been <em>pushed</em> to remote. You can also use the `git log` locally to see the commit ID and message and check if the ID matches with the most recent commit on GitHub.

# Part 2. Setting Up the Development Environment

## Step 1. Add Development Container Configuration

(1) In your `rust-tutorial` directory, create a folder named `.devcontainer`.

    mkdir .devcontainer

(2) Now, in your `.devcontainer` folder, create a `devcontainer.json` file with the following content:

    {
        "name": "Rust Development Container",
        "image": "mcr.microsoft.com/vscode/devcontainers/rust:latest",
        "customizations": {
            "vscode": {
                "settings": {},
                "extensions": ["rust-lang.rust-analyzer"]
            }
        },
        "postCreateCommand": "rustup update && rustup default stable"
    }

## Step 2: Open the Folder in Dev Container

(1) Open VSCode and install the <strong>Dev Containers</strong> extension for VScode.

(2) Press `Ctrl+Shift+P` (or `Cmd+Shift+P` on Mac),find and select "Dev Containers: Reopen in Container". This may take a few minutes while the image and requirements are being installed.

(3) After your dev container setup completes, close the current terminal, open a new terminal within VSCode, and run `rustc --version` to check if your dev container is running a recent version of Rust

## Step 3: Creating a New Rust Project

(1) Run the following command to create a new Rust project:

    cargo new hello-comp423 --vcs none

!!! info

    `--vcs none` flag is used in order to NOT create a Git repository, which it does automatically with `cargo new`

(2) Navigate to the directory we just created

    cd hello-comp423

## Step 4: Writing "Hello COMP423" Program

(1) Open `src/main.rs` file.

(2) Replace its contents with:

    fn main() {
        println!("Hello COMP423")
    }

(3) Compile the program using the following command:

    cargo build

This will compile and generate an executable in the `target/debug` directory. 

(4) Run the program:

    cargo run

You should see an output:

    Hello COMP423

!!! note
    `cargo build` compiles the project but does not run it, where as `cargo run` automatically compiles and runs the program.

