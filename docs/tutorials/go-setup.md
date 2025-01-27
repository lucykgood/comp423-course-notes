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
3. In VSCode: Click **Show Local** and navigate to the ```first-go-project``` repository you initiated in Step 1.
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
        * customizations.vscode.extensions: This VSCode extensions will help with development.

8. Open the **Command Palette** in VSCode with ```Cmd + Shift + P``` and enter **Dev Containers: Reopen in Container**. This may take a few moments, so be patient.
9. Once the setup completes and you see your Container running in the bottom left corner of VSCode, open a new Terminal in VSCode and run ```go version```. As of August, 2024, the most recent version of Go is ```1.23.0```.

## Step 4: Writing Your First Program using Go

### Initializing a Go Module and Writing Your Hello COMP423 Program

1. Open a new Terminal in VSCode.
2. Run ```go mod init first-go-project```.

    ??? note "What's happening here?"
        A **Go Module** is a collection of Go packages that share dependencies. The command you just ran  creates a ```go.mod``` module file in your project directory, which specifies the libraries and dependencies the module needs. Without a module, managing dependency versions would become very convoluted, so this modulation process is incredible important for ensuring reproducibility in the future.

3. Next, run ```touch main.go``` in your Terminal.

    ??? note "What's happening here?"
        The ```touch``` command will create a new file called ```main.go``` in your project directory.

4. Open ```main.go``` in VSCode.
5. Add the following code:
    ```go title="hello-comp423"
    package main

    import "fmt"

    func main() {
        fmt.Println("Hello COMP423!")
    }
    ```

    ??? note "What's happening here"
        * ```package main``` establishes the entry point of your program.
        * Importing the ```fmt``` package allows for the use of formatted input/output functions such as ```Println```.

Now, let's run your program. There are two ways to do this:

### Running Your Program

#### Without Building

To immediately compile and execute your program into a temporary binary *without* saving it to your disk, run the following command in your terminal:
    ```
    go run main.go
    ```
    Output:
    ```
    Hello COMP423!
    ```

#### With Building

1. To compile your program into an executable binary file, run this command in your Terminal:
    ```
    go build main.go
    ```
    
    !!! note This creates a binary file named ```main``` in your current directory. 

2. To run your newly created binary file, simply run this command in your Terminal:
    ```
    ./main
    ```
    Output:
    ```
    Hello COMP423!
    ```
3. (Optional) Deleting old/extra binary files: run ```rm main``` in your Terminal.

#### What's the Difference?

- ```go run``` is able to compile and execute code in one step. It is used for quick testing.
- ```go build``` is compiled once and is able to be ran multiple times without re-compiling.

Congratulations! You have written your very first Go program in a Dev Container that you created! Woohoo!!