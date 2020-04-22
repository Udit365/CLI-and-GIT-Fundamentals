## Basic Bash Commands

With some basic knowledge of gitbash commands, we can seamlessly work across the folder and files.

#### Working With Directories

To see the current working directory :
```bash
pwd
```

> `pwd` stands for "*Print Working Directory*".

To see the files/folders inside the working directory :
```bash
ls
```
To clear the busy command line screen :
```bash
clear
```
To change our working directory within the same drive :
```bash
cd 'directory name'
```
If there is no spacing associated with a directory name then, we can write it even without the single quotes, as follows :
```bash
cd DirectoryName
```
> `cd` stands for "*Change Directory*"

In order to change the working directory outside of the current drive, first we need to change the drive by passing the following command :
```bash
cd NewDrive:/
```
So, assuming that we are currently in the *C-drive* and want to change our location to *D-drive* then :
```bash
cd D://
```
To move to the default working directory (directory in which gitbash opens) :
```bash
cd ~
```
To create a folder/directory in the current drive :

```bash
mkdir "New Folder Name"
```
If the folder name doesn't contain space in-between then, it can be written even without the double quotes, as follows :

```bash
mkdir NewFolder
```
> `mkdir` stands for "*Make Directory*".

To make multiple folders at a time, we can write the code as follows :

```bash
mkdir Newfolder1 NewFolder2 NewFolder3
```
or,
```bash
mkdir "New Folder 1","New Folder 2", "New Folder 3"
```
To go one step back in the folders hierarchy :
```bash
cd ..
```
If we want to remove/delete a directory, then, first we need to go one step out of that directory and then use the following command :
```bash
rm -rf FolderName
```

Similarly, if the folder name contains spaces :
```bash
rm -rf "Folder Name"
```
> We can't delete the working directory thus, we need to move out to perform the remove operation.</br>
>`rm` stands for "*Remove*" and `rf` stands for "*Recursive Force*"

Operations like renaming a folder, moving a folder or, creating the copy of a folder is exactly same as renaming a file, moving a file or, creating the copy of a file as described below :

#### Working With Files

To create a new file :
```bash
touch fileName.txt
```
similarly, if the file name contains spaces then :
```bash
touch "File Name.txt"
```

To remove/delete a file :
```bash
rm filename.txt
```

To rename a file :
```bash
mv Old_filename.py New_filename.py
```
or, if the file name contain spaces :
```bash
mv "Old file name.py" "New file name.py"
```
If we want to move our file into a folder present in the current directory, i.e., inside the current directory we have our file and some other directory.

Then, we have to write the following code :
```bash
mv File_name.py ./sub_folder
```
similarly, we have to use double/single quotes, if our folder/file name has spaces in-between.

Now, if we want to move our file into a one-step-back folder then :
```bash
mv File_name.py ..
```
To move a file into some other directory :
```bash
mv filename.txt 'address of the target folder'
```
To create the copy of a file :
```bash
cp fileName.py ./new_folder
```
The above command will create a copy of the "fileName.py" in the "new_folder".
