# MODULE 2.

## What is a Shell ?

> This is the place where you should be spending your time. Some say this the heart of linux you can almost do each and everything with terminal which youcan do with GUI and more. 

## Difference between Terminal and Shell

> There is huge difference between terminal and shell but many people dont tend to know about it. A terminal is a application which invokes or provides interaction with the shell. Whereas Shell is actually the program which handles commands.

## Types Of Shell. 

1. Bash
1. zsh 
1. dash 
1. ksh
1. tsch 

## Shell Commands

### pwd

> pwd is used to find the directory in which you are in. It is quite useful sometimes as it is easy to get lost in the command line interface. 

```
$ pwd
/home/v0id
```

### cd 

> cd stands for change directory and it does exactly that it you this you can go inside a directory. 

```
$ cd Downloads
(Downloads)$
```

### ls 

> ls stands for list stuff meaning it lists each and every file and folder of present working directory. 

```
$ ls 
Applications
Desktop
Documents
Downloads
Music
Pictures
Public
Templates
text.txt
```

### touch 

> There are two instances where touch can be used: 
> 1. To create blank files. 
> 2. To change the timestamp of any file.

```
$ touch newFile
$ ls 
Applications
Desktop
Documents
Downloads
Music
Pictures
Public
Templates
newFile.txt
```

### file

> The file command can be used to find which type of file is it. Sometimes you don't know which type of file you are dealing with this command comes in handy especially with CTF's to find which type of encryption is used on a particular file. 

```
$ file module2.md
module2.md: ASCII text

$ file github_id_ed25519
github_id_ed25519: OpenSSH private key
```

### cat 
> Used to concatinate the files or display the contents of a file. 

```
$ cat 1.txt
Hello, World! 
```

### less 

> The less command is widely used in the linux world. It generally used by man pages as default view which we will see later in this section. The less command is a pager program which shows the contents file which you can navigate line by line or page by page. Another cool thing about less is that it shows the output in the terminal but as soon you leave the program the content is gone. 

```
Hello, World!
```

### history

> The history commands shows which commands have been executed recently.

```
$ history
  509  file github_id
  510  clear
  511  ls
  512  cd ..
  513  ls
  514  clear
  515  ls
  516  less test.conf
  517  history
```

### cp 

> cp stands for copy it needs two arguments first is the source file or folder and second is the destination location. 

``` 
$ touch file1
$ cp file1 ~/Downloads
$ cd Downloads
(Downloads)$ ls
file1
```

### mv 

> mv stands for move used to move files and folders. To move a file or a folder you will also need 2 arguments they are source file or folder as well destination location. 


``` 
$ touch file2
$ mv file2 ~/Downloads
$ cd Downloads
(Downloads)$ ls
file1 file2
```

### mkdir 

> mkdir stands for make directory. It used to create directories. You can create multiple directories or even subdirectories.

```
$ mkdir books
$ ls 
books 
$ mkdir folder1 folder2
$ ls 
books folder1 folder2
$ mkdir -p folder/subfolder 
$ ls 
books folder folder1 folder2
$ cd folder
(folder)$ ls
subfolder
```

### rm 

> rm stands for remove as the name suggests it used to remove files. It can remove folders too but it is recommended that you use rmdir to remove directories as you need to force the command in order to remove directories. 

Note: This command is very dangerous do not run until and unless you know what you are doing as there are some people out there who tell you to run rm -rf / "DO NOT RUN THOSE COMMANDS" it will remove your entire root system. 

```
$ ls 
file1 file2 file3
$ rm file1
$ ls
file2
$ rm -i file2
rm: remove regular file 'file2'? y
$ ls
file3
```

```
$ ls
test
$ rm test
rm: cannot remove 'test': Is a directory
$ rm test -rf
$ ls
$ mkdir -p test/subtest
$ ls
test 
$ ls test <-- This line lists the stuff of test folder directly without cd-ing into it.
subtest
```

### rmdir

> This command is used to remove directories. If a directory contains file or subfolder you will need to use '-r' switch in order to delete as by default it will only delete directories which are empty. 

``` 
$ mkdir test
$ ls
test
$ rmdir test
$ ls
$ mkdir -p test/subtest
$ ls
test
$ ls test
$  rmdir test
[v0id@tortoise test]$ rmdir test
rmdir: failed to remove 'test': Directory not empty
rmdir -r test
``` 

### find

> find is used to find stuff in a particular directory. You can even specify what type of stuff you are trying to find. 

```
$ find ~/ -name file1
file1
$ find ~/ -type d -name folder1 <-- -type d stands for directory
./folder1
$ find ./ -name README.md
./git/README.md
./CommonMark/README.md
./gotest/README.md
./README.md
```

