# Git Project

The basic Git projects are collections of beginner-friendly tasks designed to introduce participants to the fundamentals of Git, a powerful version control system widely used in software development. This practical mini-projects, and hands-on exercises will help learners quickly grasp the core concepts and confidently utilize Git in their projects.

## Initializing a Repository and Making Commits

### Initializing a Git Repository

To create a new repo, you'll use the git init command. git init is a one-time command you use during the initial setup of a new repo. Executing this command will create a new .git subdirectory in your current working directory. This will also create a new main branch.

**Steps to initialise a git repo :**

1. Open a terminal on your computer e.g git bash or vs code.
2. On the terminal, create a working folder or directory e.g `mkdir PROJECT2`
3. Change into the working directory using `cd PROJECT2`
4. While inside the folder, run `git init` command.

![Alt text](<images/Git init.png>)

### Making the first commit

Commit is more or less saving the changes made to a file. Changes can be adding, modifying or deleting a file or text. When you make a commit, git takes a snapshot of your current repository and saves a copy in the .git folder inside your working directory. 

**Steps to make a first commit :**

1. Inside your working directory create a file index.txt using this command `touch index.txt`

2. Write any sentence of your choice inside the text file. Afterwards save the changes.

3. Add your changes to the git staging area using this command `git add`

4. To commit your changes to git, run the command `git commit -m "first commit"` (The -m flag is used to provide a commit message).

![Alt text](images/commit.png)


## Working with Branches

### Working with Branches

A key feature of Git is branching. Think of the trunk of a tree as your main project. We create branches to separate our work for each task. It helps us isolate and work on one part of the project without directly impacting the main project until we are ready to merge it back in.  
Git branch helps you create a different copy of your source code. In your new branch, you can make changes as you please. Your change is independent of what is available in the main copy. 

Git branch is also an important tool for collaboration with remote teams. They can make separate branches while working on the same feature and then converge their code to one branch when they are all done.

### Make your first git branch

Syntax

`git checkout -b` 

To make a new branch called oak, run the command :

`git checkout -b oak`

![Alt text](<images/git branch.png>)

### Listing your git branches

To list the branches on your local git repositories, run

` git branch`

![Alt text](<images/git branch list.png>)

### Change into an old branch

To change into an old branch, use the command below

` git checkout <branch-name>`

![Alt text](<images/git branch switch.png>)

### Merging a Branch into another Branch

If we have 2 branches A and B and want to merge the contents of branch B into branch A, we first change into branch A and run the command below :

` git merge B`

![Alt text](<images/git merge.png>)


### Deleting a git branch

A feature branch enables the addition of a new feature to an application. After the code has been tested and merged into a staging of dev environment depending on the branch strategy of the team, the branch can be deleted using the below syntax :

` git branch -d <branch_name>`

![Alt text](<images/git branch delete.png>)


## Collaboration and Remote Repositories

In addition to all the functions above, git can also be used for collaboration amongst remote workers by using a remote repository such as github, a web-based platform where git repositories are hosted. Thus remote teams can now view, update, and modify the same repository.

### Creating a Gitnub Account

To create a Github account, follow the below steps :

1. Go to Github website

   *[ Join Github](https://github.com/)*

2. Enter you username, password and email

![Alt text](<images/github login email.png>)

3. Click on the verify button to solve a puzzle 

![Alt text](<images/verify account.png>)

4. Click on create account

![Alt text](<images/verify account2.png>)

5. Enter the activation code sent to your mail

![Alt text](<images/activation code.png>)

6. Select your preferences and continue

![Alt text](images/preferences.png)

7. Select features you are interested in and click on continue.

![Alt text](images/features.png)


### Creating your first repository

To create your first repository, follow the steps below :

1. In the upper-right corner of any page, use the drop-down menu, and select New repository.

![Alt text](<images/Github create repository.png>)

2. Type a short, unique name for your repository, add a desciption (optional), and select whether it is a public or private repository.

![Alt text](<images/Github create repository_form.png>)


3. Click on the green button to create a repository.


### Pushing your local git repository to your remote github repository

To add a remote repository to a local repository, use the command :

`git remote add origin <link to your github repo>`

![Alt text](<images/git remote add origin.png>)

To get the remote link, click on the green button and copy the https link as shown below :

![Alt text](<images/git remote add origin link.png>)

After committing changes in the local repo, push to the remote repository using the command below : 

`git push origin <branch name>`

![Alt text](<images/git push.png>)


### Cloning remote git repository

The git clone command helps us to make a copy of our remote repository on our local machine. The syntax is as below :

`git clone <link to your remote repository>`

![Alt text](<images/git clone.png>)


## Branch Management and Tagging

### Introduction to Markdown Syntax

Markdown is a lightweight markup language for creating formatted text using a plain-text editor. John Gruber created Markdown in 2004 as a markup language that is easy to read in its source code form. Markdown is widely used for blogging and instant messaging, and also used elsewhere in online forums, collaborative software, documentation pages, and readme files. 

Some commonly markdown syntax are as below : 

- Headings: The number of hash symbols used indicates the level of the heading.
  ```
     # Heading 1
     ## Heading 2
     ### Heading 3


- Emphasis: Asterisks or underscore is used to emphasise texts. 

`*italic* or _italic_`
`**bold** or __bold__`

- Ordered list
   1. First item
   2. Second item
   3. Third item


- Unordered list

    `- Item 1`

    `- Item 2`

    `- Item 3`


- Links : To create links, use the square brackets for the link text followed by parenthesis containing the url.

`[visit darey.io](https://www.darey.io)`

- Images : To display an image, use an exclamation mark followed by square brackets for the alt text and parenthesis for the image url.

`![Alt Text](https://example.com/image.jpg)`

- Code : To display code, use backticks (`) to enclose the code.















