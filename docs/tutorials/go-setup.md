# **Tutorial for Setting Up a Dev Container for Go and Making a Program**

#### Primary author: [Ram Ariga](https://github.com/bariga04)
#### Reviewer: [James Masterson](https://github.com/James-Masterson)  
  
Hello Readers! The following tutorial is a guide to create a simple project in the programming language **Go**.  
  

Follow the steps as listed and you'll be on your way to making a **Go** program in no time!  



## Prerequisites:  

- Programming experience   
- Git installed: can install it [here](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)   
- Have **VSCode** installed 
- A command terminal  
- A GitHub account  
- Docker installed 


## Step 1. Setting up your project

- Open your command terminal and `cd` to your home directory. Then make a new directory and cd into it.  
!!! note  
    This should be your project root folder  


```bash  
cd  
mkdir <directory name>  
cd <directory name>  
```  
  
### Setup GitHub:  

- Create a git repository with this command:

```bash
git init  
```

- Then create a GitHub repository on the GitHub website by going to the repositories page and clicking the **"new"** button.
    - Make sure to **NOT** initialize with a **.gitignore** or **license** or **`README.md`**  
- Make sure to then link your local git repository to the remote repository in your GitHub acccount with this subcommand:  

```bash  
git remote add origin <link to repository>.git  
```  

## Step 2. Create your dev container  

-  Install the **Dev Containers extension** on VSCode  
-  Open up your project folder in VSCode  
-  Create a new directory called `.devcontainer` and a file inside of it called `devcontainer.json` 
  -  The `devcontainer.json` file will contain configurations for the container. In this case we will have a image and extensions that correlate with the Go programming language. This file will also install the Go extension in VSCode.
-  The `devcontainer.json` file should look something like this:  

```js  
{
  "name": "<Project Name>",  
  "image": "mcr.microsoft.com/devcontainers/go:latest",  
  "customizations": {  
    "vscode": {  
      "settings": {},  
      "extensions": ["golang.go"]  
    }  
  },  
  "postCreateCommand": "go mod tidy"  
}  
```  
!!! warning  
    After you finish your `devontainer.json` file make sure to save it.  
- Then reopen the project in the container. VSCode should prompt you to do this but if not use `Ctrl+Shift+P` then type **"Dev Containers: Reopen in Container"** in the search bar then select the option it shows.  


## Step 3. Creating a Go "Hello Comp423" program  

-  Before starting the next step, make sure you have an up to date version of Go installed using the **`go version`** subcommand   
- Open up a new terminal in VSCode. You will be using this terminal from now on.  
- First use the `go mod` subcommand to create a go module. Name it the same name as your project if you'd like for convenience.    

```go  
go mod init <module name>  
```  

- In your project root folder create a new .go file. You can name it anything you want, for example: `hello423.go`  

!!!  note  
    Your file should contain the following:  

```go  
package main

import "fmt"

func main() {
    fmt.Println("Hello COMP423")
}  
```  

## Step 4. Run your program!  

- Now that you have your .go file, you can run your program using the `run` subcommand! 

!!! note   
    Type the following in your VSCode terminal:  

```go 
go run .  
```  

-  If you did everything correctly you should see **`Hello COMP423`** displayed in the terminal.  

### Using build subcommand:  

-  An alternative way to run the program is to use the `go build` subcommand. Unlike `go run`, the build subcommand creates a binary executable file that you can run directly by typing `./<executable name>` in the terminal. This is similar to the `gcc` command in Comp 211, where you first compile a `.c` program into an `.o` file then into an exectuable file that can be run.  
  -  This differs from the `go run` subcommand as the `run` subcommand compiles and runs the program in one step with no exectuable file saved in the project folder.  
  
-  The following terminal commands detail the process. In this case the `.go` file is called `hello423.go`  

```go  
go build hello423.go  
./hello423  
```  
!!! note  
    This should also print **`Hello COMP423`**  

### Clean up dependencies:  

!!! warning  
    Use the `go mod tidy` subcommand to clean up any uneeded dependencies after running your program.  

**Congrats on making it to the end! You're officially a Go programmer!**