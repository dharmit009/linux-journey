# Module 3

There are three types of streams they are as follows: 

1. Standard Out (stdout)
1. Standard In (stdin)
1. Standard Error (stderr)

## Standard Out (stdout)
```
$ echo "Hello, World" > hello.txt
$ cat hello.txt
Hello, World
```

Let's break this down into different parts: 

1. echo "Hello, World": This line states that print "Hello, World" to the console or echo back. 

2. > (Overwrites): This symbol indicates that whatever standard output you get from the previous command redirect towards something.

3. hello.txt : The standard out is redirected into a file known as hello.txt which basically means hello.txt will have a string Hello, World.

### Overwrites (>):
```
$ echo "Hello, World" > hello.txt
$ echo "Hello, World" > hello.txt
$ cat hello.txt
Hello, World
```

### Appends (>>):
```
echo "Hello, World" >> hello.txt
$ cat hello.txt
echo "Hello, World" >> hello.txt
$ cat hello.txt
Hello, World
Hello, World
```

*Note:* When you put single '>' it overwrites the entire file. So it is always recommended to use double '>>' as it appends the data into the file.

## Standard In (stdin):

The stdin stream is used to get inputs from different sources. A computer takes our input from the keyboard likewise we can give input to program or process through a file or even output of other processes.

```
$ cat < hello.txt > hello2.txt
$ cat < hello2.txt 
Hello, World
```

## Standard Error (stderr):

The standard error is used to redirect error messages. Note it may look like that error messages and standard output are one and the same but they are not as stderr only redirects error messages like command not found, whereas stdout only redirects output (things which have been executed successfully).

To redirect stderr we need to use '2>'.

```
$ ls /fake/directory > hello.txt 
$ cat hello.txt
$ ls /fake/directory 2> peanuts.txt 
$ cat hello.txt
ls: cannot access /fake/directory: No such file or directory
```

*Note:* Shorter Way to redirect both stdout and stderr (&>).

## Pipes (|) and Tee:

1. pipes (|): Pipes are used to redirect one processes output to another processes input. 

2. tee: It is used to redirect output on both CLI as well to any other process or file. 

```
$ ls /file | tee hello.txt
ls: cannot access '/file': No such file or directory
$ cat hello.txt
ls: cannot access '/file': No such file or directory
```

## Environment variables: 

There are tons of predefined Environment variables in linux here are some of them: 

```
echo $HOME
/home/hmm
echo $USER 
hmm
echo $PATH 
/home/hmm/.local/bin:/usr/local/bin:/usr/bin:/var/lib/snapd/snap/bin:/usr/local/sbin:/usr/lib/jvm/default/bin:/usr/bin/site_perl:/usr/bin/vendor_perl:/usr/bin/core_perl
```

*To find more such environment variables use command `env`.*

## CUT: 

The cut command does exactly what is says it cuts !! heheh..
Here are a few switches of cut and their working: 
-c stands for cut through number of characters. 
-f stands for cut through number of fields. 
-d is used to provide custom delimiter or divider.

```
$ echo "Hello, World! I am computer" > hello.txt
$ cut -c 4 hello.txt # note cut -c counts from 1 not 0. 
l
$ cut -f 2 hello.txt # note cut uses tabs by default so human error.
Hello, Worldcat hello.txt I am computer
$ cut -f 1 -d ',' hello.txt # custom delimiter.
Hello
```

## paste: 

The paste command is used to merge lines together in a file.

```
$ cat test.txt
The
quick 
brown 
fox

$ paste -s test.txt
The	quick 	brown 	fox	

$ paste -d ' ' -s test.txt
The quick  brown  fox 

```

## head & tail: 

Both of the commands can be used to print a few lines of file top and bottom using head and tail respectively. They come in very handy while looking at log files. You can change the number of lines by using the `-n` switch.

```
$ head /var/log/syslog
...
Outputs first 10 lines of log file.
...
$ tail -n 5 /var/log/syslog
...
Outputs last 5 lines of log file.
...
```

## expand & unexpand: 

The commands expand and unexpand are used to convert TABS into spaces or vice versa. 

file1.txt
1 John
2 Jane
3 Mary

file2.txt
1 Doe
2 Doe
3 Sue

```
$ join file1.txt file2.txt
1 John Doe
2 Jane Doe
3 Mary Su
```

## sort: 

`sort` command is used to sort anything in order.

## tr: 

$ tr a-z A-Z
hello
HELLO

## uniq: 

`uniq` is used to print all the unique lines from a file. 

## wc and nl: 

`wc` - word count.
`nl` - counts number of lines.

## grep: 

`grep` is used to grep words and strings. It is a super useful command to find a needle from a hay stack.






