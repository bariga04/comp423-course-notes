# **Setting up a dev container for Go**

#### Primary author: [Ram Ariga](https://github.com/bariga04)
#### Reviewer: [James Masterson](https://github.com/James-Masterson)


## Prerequisites:  

- Programming experience   
- Git installed: can install it [here](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)   
- Text editor. **VSCode** is highly recommended  
- A command terminal  
- A GitHub account


## Step 1: Install Go

- Click on this [link](https://go.dev/doc/install) to install Go. Follow the steps listed in the linked website.  


## Step 2: Setting up your project

- Open your command terminal and cd to your home directory. Then make a new directory and cd into it.

```bash  
cd  
mkdir <directory name>  
cd <directory name>  
```  
  
- Create a git repository with this command:

```bash
git init  
```

- Then create a GitHub repository on the GitHub website by going to the repositories page and clicking the **"new"** button.
    - Make sure to **NOT** initialize with a **.gitignore** or **license**    
- Make sure to then link the git repository to a remote repository in you GitHub acccount with this subcommand:  

```bash  
git remote add origin https://github.com/<your-username>/comp423-course-notes.git  
```  


### **Make sure to enable dependency tracking** 
- This is to track modules you import packages from

```Go  
$ go mod init <module name>
go: creating new go.mod: module <module name>
```

## Step 3: Create your dev container  



