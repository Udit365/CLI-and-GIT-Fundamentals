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

#### Staging & Committing Changes

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

We can directly commit the changes ,i.e., we can skip the staging step by passing the following command -:

```bash
git commit --all
```
or,

```bash
git commit -a
```
> `-a` or, `--all` removes the need of staging of files.

To provide a message during direct commit, we can pass the code as follows :
```bash
git commit -am 'Minor edits'
```
To provide multiline commit message, we have to pass the `commit` command without `-m` as follows :
```bash
git commit -a
```
The above command will throw the following message on the screen and after a few seconds, it will open a window on the default editor to type our multi-line commit message :
```
hint: Waiting for your editor to close the file...
```

The following convention is generally followed for a multiline commit message :

```
Here goes the commit brief

A little descriptive commit message trhat explains the commit heading
```
After writing our commit message, we have to save and close the file and after that, git will show the heading of our commit message in the command window.

#### Commit Message Best Practices




#### Viewing Commit

To view the commits made to the repository, we need to pass the following command :

```bash
git log
```
If we have many multi-line commits, then, the output of the above command will appear a bit messy. So, if we want to see the commits only with the commit headers, then we can pass the following command :
```bash
git log --oneline
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

#### Viewing Changes

To view what changes we have made, we have to pass the following code :
```bash
git diff
```
By executing the above code, we can only able to see the changes and not the entire document.

To view the changes in the staged files, we have to pass the following command :

```bash
git diff --staged
```
or,

```bash
git diff --cached
```
If we want to see the changes as highlighted texts, then we can pass the following command -:

```bash
git diff --color-words
```
similarly, for staged files :

```bash
git diff --staged --color-words
```
To view what we have done in a specific commit then, we have to pass the following command :

```bash
git show 1c16945
```
> Each commit has a unique commit ID associated with it and by passing the first few characters(6-8 characters) of that ID, `git show` command is able to identify the correct commit and shows us the change.

Similarly, to see the changes made in the last commit, we can pass the `HEAD` instead of the unique commit ID :

```bash
git show HEAD
```
When there is multiple and lots of changes then, gitbash uses a paginator (`:` symbol) after showing a certain number of changes and we can use `F` and `B` keys or, `Spacebar` to see further lines.

To toggle between wrapping and chopping of long lines we can type `-` and then hit the `Enter`.

To quit this paginator view, we have to use the `q` key.

#### Comparing Changes

To compare any two commits, we can pass the following command :

```bash
git diff 1c16945..9dcff6ef6
```
> The first few initial characters of unique commit IDs are separated by `..` in the above code

Similarly, to compare the changes in the last made commit with some other commit, we can pass the following command :

```bash
git diff 1c16945..HEAD
```

To view the comparison as highlighted texts :
```bash
git diff 1c16945..HEAD --color-words
```








#### Tracking File Deletion

There are two ways by which we can track the changes due to deletion of a tracked file (committed/staged).

- Removing file manually
- Removing file through Git

***Removing file manually***

We can manually delete the file using gitbash CLI or, by interacting with GUI.

*Using the gitbash CLI, we can remove the file as follows :*
```bash
rm FileName.txt
```
Now to commit this change, we have to pass the following code :

```bash
git rm FileName.txt
```

The above code will put the change in staging area and then, we can commit this change as usual :

```bash
git commit -m "Deleted the file named FileName.txt"
```

***Removing file through Git***

Rather than manually deleting a file and then committing that change, we can directly delete the file using git specific command and then commit it as usual.

The following code deletes the file from the directory and adds the change in the staged area as well :

```bash
git rm FileName.txt
```
Then, we can commit the change as follows :

```bash
git commit -m "Deleted the file named FileName.txt"
```

#### Moving & Renaming Files

Just like deletion operation, we can perform renaming and moving of files in two ways but, its more convenient to perform this using git specific command.

For git, moving and renaming of a file and essentially the similar kind of changes.

So to rename a file through git specific command, we need to pass the following command :

```bash
git mv FileName.txt NewFileName.txt
```
The above code will rename the file and add it to the staged area and then we can commit the change as follows :

```bash
git commit -m "Renaming the file"
```

Now, if we would have renamed the file manually then, we have to pass the following command to stage the changes :

```bash
git rm FileName.txt
git add NewFileName.txt
```
Similarly, to move a file to some other folder in the directory, we can use the following git specific command :

```bash
git mv FileName.txt Subfolder/FileName.txt
```

Then, we can commit the changes as follows :

```bash
git commit -m "Renamed and moved file name"
```
