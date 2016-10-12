# GitHub for Beginners: Open source your python project

In this talk, we'll cover how to use git at the command line level to unleash the full power of git as a version control for your codebase. This tutorial assumes you have a basic knowledge of the command line, the git package installed (brew install git; yum install git; apt-get install git), and a desire to learn new things.

## Key Concepts & Verbiage

There are many terms and concepts that the savvy git user knows but to start your git career you only need to know two primary concepts: **commits** and **repositories**.

### Commit

A commit is the act of creating a snapshot of the current state of your code. 

 - is a record of what files you have changed since the last time you made a commit
 - used as a verb/noun: "I just committed some code", "Check out the latest commit"
 - essentially a project is a collection of commits
 - sometimes colloquially referred to as "changes"

### Repositories (often shortened to "repo")

The directory where you access your project, its files, and all the version of its files (*commits*).  

 - Repositories can live both on your local machine and on remote servers (GitHub)
 - The act of copying a repository from a remote server to your local machine is called **clone**-ing.
 - Downloading commits that don't exist on your local machine from a remote repository is called **pull**ing changes.
 - Uploading commits that you have on your local machine to a remote repository is called **push**ing changes.
 - Think of the remote repository (GitHub) like DropBox... it synchronizes commits accross all local machines.

If these terms are still confusing to you, don't worry about it. The best way to learn something is to just do it. Let's get our hands dirty...

## Creating Your First GitHub Project

For our first github project, we're going to cover a few things. First, we're going to learn typical git project flow of creating, editing, and maintaing python source code. Secondly, we're going to learn some simple yet critical git commands to control our repository. And thirdly, we're going to learn the basic python package structure for organizing python code. 

Our first github python project is going to be a basic math implementation of addition and subtraction. Let's call this project pyrva-math. Let's go through the various steps of creating this project.

### 1. Create the top level project directory.

This top level directory will contain your python source code, git repository, environments, etc. It's the root directory of your project.

```shell
mkdir -p /any/path/to/project/pyrva-math  # create the directory
cd /any/path/to/project/pyrva-math  # change to that directory you just made
```

### 2. Initialize our git repository

Every git command that you run from now on out will begin with ```git``` and include a succeding command dictating what you want git to do. The command that tells git to initialize a new repository is abbreviated as ```init```. ```git init``` tells git to create a new repository at the current working directory. 

If you're unsure where your terminal is at any given point in this tutorial, you can always run the bash command ```pwd``` (this tells you **p**resent **w**orking **d**irectory you are in). 

Let's go ahead and create that git repository...

```shell
git init
```

Easy eh?

### 3. Implement our add and subtract functions

Create a file named pyrva.py within your working directory. You can do this directly in your terminal by running the command ```touch pyrva.py```. We're going to implement our complicated math functions as follows:

```python
def add(x, y):
    return x + y

def subtract(x, y):
    return x - y
```

In fact, instead of opening up a text editor, we can write our code into pyrva.py using bash!

```bash
echo """def add(x, y):
    return x + y

def subtract(x, y):
    return x - y""" > pyrva.py
```

Once you go bash, you never go back.

### 4. Check the status of our repository

Let's see if git notices that we created a new file in the directory. Probably the most type git command is ```git status```. ```git status``` gives you information about the current state of your project. It informs you on new files created, changes between current files and the last commit, and other pertinent information we won't delve into at the moment.

Go ahead and try ```git status```. You'll see something like the following:

```
MacBook-Pro-2:github robert$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Untracked files:
  (use "git add <file>..." to include in what will be committed)

	pyrva.py

nothing added to commit but untracked files present (use "git add" to track)
```

Under untracked files, you see our newly created file ```pyrva.py```. In git speak, untracked files refer to files that are newly created in the workspace. git has no prior record of that file and therefore is not currently tracking its changes.

### 5. Add pyrva to a commit

To have git keep track of our changes to ```pyrva.py```, we have to commit the file to our local repository so it can keep track of the file going forward. To add the file to a commit, yup you guessed it, we need to run the command ```git add``` and list the file names we wish to add. 

```bash
git add pyrva.py
```

Note you can add as many files as you want to a commit. Commits are not limited to just one new file or one line changes. We'll explore that a little further down.

Try running ```git status``` now and note the difference:

```
MacBook-Pro-2:github robert$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	new file:   pyrva.py
```

Cool beans.

### 6. Commit!

Let's commit the new ```pyrva.py``` file to our repository. 

``` git commit -m "Implemented pyrva.py"
```

Note 

7. Modify our math module to abstract to infinite arguments

8. Save our changes to a commit

9. Commit!

10. Push our local repository to github

11. Let's create a README on github so we have documentation

12. Module vs. Package

13. Create the add module

14. Create the subtract module

15. Save our changes to a commit 

16. Push our commit to github

17. Wait what happened?? Merge???

18. Pulling 

19. Merging conflicts

20. Push 

## Python Virtual Environment

"A Virtual Environment is a tool to keep the dependencies required by different projects in separate places, by creating virtual Python environments for them. It solves the “Project X depends on version 1.x but, Project Y needs 4.x” dilemma, and keeps your global site-packages directory clean and manageable. For example, you can work on a project which requires Django 1.3 while also maintaining a project which requires Django 1.0." 

### Installation 

Installing virtualenv for python is as simple as the following few steps:

    pip install virtualenv
    # cd to your project and create a virtualenv
    cd /path/to/project
    virtualenv -p python3 env 
    source env/bin/activate  # activates the virtualenv within your terminal session
    pip install pyrva  # install your packages within the virtual environment
 
### requirements.txt file

Most python open source packages have a requirements.txt file at the root of the project directory that denotes the required packages the project requires for runtime. Pip has a convenient way of installing packages from a text file:

    # cd to your project and create a virtualenv
    cd /path/to/project
    source env/bin/activate  # ensure you're within your virtual environment
    pip install -r requirements.txt  # installs packages listed in the requirements.txt file

A current list of installed packages your project currently has in its virtual environment can be viewed by running

    pip freeze
    
An up to date ```requirements.txt``` file can be obtained by running at your project directory level

    pip freeze > requirements.txt 


## Python Setup Tools


## Pytest


## Putting It All Together

We're going to modify our pyrva-math module to include some more advanced functionality not already support by native python functions. In doing so, we'll include a python package called numpy to demonstrate using external libraries in an open source project. 

1. 

## Additional Resources

 - [Interactive tutorial](https://try.github.io/levels/1/challenges/1)
 - [Visual Guide To How Git Works](http://marklodato.github.io/visual-git-guide/index-en.html)
 - [Learning Markdown](https://guides.github.com/features/mastering-markdown/)
 - [Forking Existing Projects](https://guides.github.com/activities/forking/)
 - **Advanced** [Uploading Project to PyPi](http://peterdowns.com/posts/first-time-with-pypi.html)
