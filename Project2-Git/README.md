This is my step by step process of following instructions for the Git project. 

It contains my successes, as well as my failures and how I resolved them.

## Step 1 

- I opened my Git bash terminal 
- Used `cd` to change directory to folder I wanted to work from
- used `mkdir`to create my proposed repo folder and used cd to move into it. 
- used git init to initialise local repo

![Alt text](<images/Create and init Git.png>)

## Step 2

- Used the `touch` command to create a file named

- Manually added text and used `cat` to display the contents

- Used `git add .` to move changes to staging area

- Used `git commit -m "initial commt"`the `-m `flag was used to create a commit message `"initial commit"`

![Alt text](<images/Create file and Git commit.png>)


## Step 3

- Create new branch with the `git checkout -b`where `-b` was used to specofy the branch name as `my_new_branch`

![Alt text](<images/Create new branch.png>)

## Step 4

- Create new file in that branch and assign text with the `echo <file content> > <filename.txt>` command. 

- Used `git add` and `git commit -m` to stage and commit the new file.

## Step 5

- Used `checkout` to move to main branch

- Used `git merge <name of new branch>` to fuse both branches together. 

![Alt text](<images/merge branches.png>)

## Step 6

- Used `ls` to show the new files in the main branch

- Used `git branch -d <branch_name>` to delete created branch

![Alt text](<images/Branch merge and remote add.png>)

# Collaboration

Already had a github account

## Step 1

Created a fresh repo to test out collaboration techniques

![Alt text](<images/Create new repo.png>)


- Used `git remote add origin <repo link>`to add the new github repo to my local repo

## Step 2

- Tried pushing with `git push origin main` but it failed. The github repo had a file (a readme.md) file that I didn't have locally

![Alt text](<images/First trial git push failed.png>)

## Step 3

- I used the `git pull origin main` to pull the file from the github repo

- It didn't merge unrelated histories so I used `git pull origin main --allow-unrelated-histories`

![Alt text](<images/GIt pull and allowing unrelated histories .png>)

## Step 4

- The I used the `git push origin main` to push again and it was successful. 

![Alt text](<images/successful git push.png>)

## Cloning a repo

Since I already merged the newly minted repo, I decided to create a clone of an old pyhton project I did -- A love calculator

### Step 1

- I used `cd` to change directory to a folder outside of the repo folder I was working with

### Step 2

- I copied the https link of the 'love calculator' repo on my github account

- I used the `git clone <remote repo link>`to clone the repo to my local pc

![Alt text](<images/Git clone love calculator.png>)

Markdown syntax

### 1 Use the Hash symbol to create headings. Number of has symbols determines headings level

# Heading 1

## Heading 2

### Heading 3

### 2 Emphasis

Used asterik and underscore to emphasise text. Single for italic and double for bold. 

*italic* or _italic_

**bold** or __bold__

### 3 Lists

underoded lists and orderd lists

unordered lists

- Item 1
- Item 2
- Item 3

ordered list
1. First item
2. Second item
3. Third item

### 4 hyperlinks

Used square brackets for link tests, followed by paranthesis for the url
[visit darey.io](https://www.darey.io)

### 5 To display image

An exclamation mark followed by square brackets for the alt textr and paranthesis for image url

![Alt Text](https://example.com/image.jpg)

### 6 display code

Use backticks to enclose the code

`console.log('Welcome to darey.io')`







