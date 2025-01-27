# Creating Your First Project with Go!

* Primary Author: [Lucy Good](https://github.com/lucykgood)

* Reviewer: [Maddie Clark](https://github.com/mbclark37)


## Step 1: Getting Started

During this tutorial, you will create your first project using Go!
In this tutorial you will learn how to:

1. Create and initialize a Git repository for your project
2. Set up a Development Container in VSCode
3. Create your first "Hello COMP423" program using Go

### Before You Begin
1. Ensure that you have [Git installed](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) on your computer.
2. Ensure that you have [VSCode installed](https://code.visualstudio.com/) on your computer.
3. Ensure that you have [Docker installed](https://www.docker.com/products/docker-desktop/) on your computer.
4. Get excited because you are about to learn some major knowledge.


## Step 2: Creating and Initializing your Project Repository

1. Open your Terminal.
2. Navigate to the file folder on your computer where you would like this project to be stored.
3. Create a new directory.
   ```
   mkdir first-go-project
   cd first-go-project
   ```
4. Initialize your new directory as a Git repository.
   ```
   git init
   ```

## Step 3: Starting Your Dev Container in VSCode

1. Open VSCode on your computer.
2. In your computer's menu: File -> Open
3. In VSCode: Click **Show Local** and navigate to the repository you initiated in Step 1.
4. Install Microsoft's **Dev Containers** extension on the **Extensions** tab of VSCode's side bar.
5. In the root of your project directory, create a folder called ```.devcontainer```.
6. In this folder create a file called ```.devcontainer.json```.
7. In this new file add the following code: 
    ```json title="dev-setup.json"
        {
            "name": "Go Development Environment",
            "image": "mcr.microsoft.com/devcontainers/go:latest",
            "customizations": {
                "vscode": {
                    "extensions": [
                        "ms-vscode.go"
                     ]
                }
            }
        }
    ```
    !!! note "Explaining .devcontainer.json"
        * name: Choose a name for your development environment. Ensure that it is recognizeable and unique.
        * image: `mcr.microsoft.com/devcontainers/go:latest` is Microsoft's official replica of the exact development environment required for Docker.
        * customizations.vscode.extensions: These VSCode extensions will help with development.
8. 