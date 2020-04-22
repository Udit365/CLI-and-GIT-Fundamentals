## Basic Git Commands

To initialize a repository, first we need to create a directory in a place of our choice in the hard drive and then, we have to make it as our current working directory.

#### Initialize a git repository

Let's say, we want to initialize a repository in a folder named "New_Project" in *D-drive* :

```bash
cd D://
mkdir New_Project
cd New_Project/
```
Now, to initialize "*New_Project*" as a repository :

```bash
git init
```
The repository contains some `.git`, `..` files (Used for version control) which are hidden by default and in order to see them, we have to pass the following command :
```bash
ls -la
```
similary, the `.git` file contains many other directories and files inside that helps git in tracking.

To view those files and folder :
```bash
ls -la .git
```
To see our configuration for the repository, we need to pass the following command :
```bash
ls -la .git/config
```
if we remove the `.git` from the repository then, it will no longer remain as a repository and work as an ordinary folder.

#### Committing Changes

To see how git keeps track of the changes made in the file, first we need to make some changes like creating a new file or, editing a file etc. and commit them.

Let's first create a simple text file and save it in the respository

```bash
touch My_file.txt
```
Now, after editing and saving the changes, we need stage the file to git as follows :

```bash
git add .
```
With `.` sign, we tell git to stage all changes in the current directory.

To stage a single file, we need to pass the following code :

```bash
git add My_first_file.txt
```
>If the file name has spaces then, we should enclose it within single/double quotes.

Similarly, we can stage multiple files by separating the file names with spaces, as follows :

```bash
git add MYfile1.txt NextFile.py 'Hello world.py'
```
Now, we need to commit the changes, so that git can track the changes :

```bash
git commit -m "Initial Commit"
```

#### Commit Message Best Practices




#### Viewing Commit Log

To view the commits made to the repository, we need to pass the following command :

```bash
git log
```
 To view commit log since a certain date :

 ```bash
 git log --since=2020-01-01
 ````
 The above code will show all the commits made since 1st January 2020.

 Similarly, instead of `since`, we can use `until` as a date filter to our commit log message :

 ```bash
 git log --until=2020-01-01
 ```
The above code will show all commits made since 1st January 2020.

To filter commit log by author :
```bash
git log --author="Kevin"
```
The above code will show all the commits made by *Kevin*, however, we can also write the part of the author name as well to get the same result.

For example, we can write the following command to get all the commit log by *Kevin* :

```bash
git log --author="Kev"
```
To filter commit log by the first few sentences of the commit message :

```bash
git log --grep="Init"
```

The above code will return any commit that has "*Init*" string in the commit message.

> `grep` stands for "*Global Regular Expression*"

#### Viewing Current Status

Anytime if we want to see the status of our git project then, we can just pass the following command :
```bash
git status
```
