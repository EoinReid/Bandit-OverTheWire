# Bandit-CTF
OverTheWire Bandit is a linux based Capture the Flag wargame designed for beginners to dive into the world of Linux, Networking, Cybersecurity and Capture the flag wargames. This is where I will publish my walkthroughs and progress through the Bandit Capture The Flag.

# Levels
- [Level 0](#level-0)
- [Level 0 → Level 1](#level-0--level-1)
- [Level 1 → Level 2](#level-1--level-2)
- [Level 2 → Level 3](#level-2--level-3)
- [Level 3 → Level 4](#level-3--level-4)
- [Level 4 → Level 5](#level-4--level-5)
- [Level 5 → Level 6](#level-5--level-6)
- [Level 6 → Level 7](#level-6---level-7)
- [Level 7 → Level 8](#level-7---level-8)
- [Level 8 → Level 9](#level-8---level-9)

# Level 0

### Level Goal

> The goal of this level is for you to log into the game using SSH. The host to which you need to connect is [bandit.labs.overthewire.org](http://bandit.labs.overthewire.org/), on port 2220. The username is bandit0 and the password is bandit0. Once logged in, go to the Level 1 page to find out how to beat Level 1.
> 

### Walkthrough

We are told in the level goal we will need to log into the game server using the SSH command.

In the level goal with are also provided with the host address, it’s port number, as well as the username and password.

We can construct our SSH command using this information like so:

```bash
ssh -p 2220 bandit0@bandit.labs.overthewire.org 
```

After running the command we will be prompted to enter a password to continue to the level, this password is bandit0 as stated in the level goal above.

![bandit0-2.PNG](https://github.com/EoinReid/Bandit-OverTheWire/blob/main/bandit-screenshots/bandit0-2.png)

### Flag

There isn’t a “flag” perse for this level as the goal was to successfully connect to the game server via SSH.

### Commands breakdown

Let’s break down the command we used for this level so we can understand each part of it.

```bash
ssh -p 2220 bandit0@bandit.labs.overthewire.org 
```

```bash
ssh
```

> Secure Shell (SSH) is a cryptographic network protocol for operating network services securely over an unsecured network.
> 

```bash
bandit0@bandit.labs.overthewire.org
```

> Bandit0 is the username we were given in the level goal descriptor and [bandit.labs.overthewire.org](http://bandit.labs.overthewire.org/) is the server address we want to connect to so we specify we want to connect to that address with the bandit0 username using the @ symbol inbetween them.
> 

```bash
-p 2220
```

> The -p attribute is used to specify a port number for our command as we were given the port number 2220 in the level goal descriptor, we needed to specify this in our command.
>


# Level 0 → Level 1

### Level Goal

> The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level,logout of your existing SSH session,then use SSH (on port 2220) to log into that level and continue the game.
> e.g. To move from Level 0 (Bandit0) to Level 1 (Bandit1)

```bash
logout
```

```bash
ssh -p 2220 bandit1@bandit.labs.overthewire.org
```
Then when asked for the password, enter the flag from the previous level.


### Walkthrough

We are told in the level goal descriptor that the password for the next level is stored in a file called readme in the home directory. So first we need to check if we are in the home directory. We do this using the `pwd` command.

After the `pwd` command confirms we are in the home directory we need to list the contents of the directory to see what's there we do this using the `ls` command.

From the `ls` command we can see there is a file called "readme" in the home directory, so we are going to use the `cat` command to see the contents of this file.

We have now captured our flag for this level and obtained the password.

![bandit0-01.png](https://github.com/EoinReid/Bandit-OverTheWire/blob/main/bandit-screenshots/bandit0-01.png)

### Flag

```bash
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
```

### Commands breakdown

```bash
pwd
```

> pwd or Print Working Directory does what it says on the tin, it prints the working directory aka the directory you are currently in to the terminal to let you know where in the file system you are located.
> 

```bash
ls
```

> ls or List Directories is a command used to list directories and files in the current directory by default, however you can specify which path you want to list the directories of.
> 

```bash
cat readme
```

> cat, short for concatenate is a command that not only displays file contents but it can combine multiple files and show you the output of them. In this instance the file in the directory we needed to read was called "readme".
> 

# Level 1 → Level 2

### Level Goal

> The password for the next level is stored in a file called - located in the home directory.
> 

### Walkthrough

We are told in the level goal descriptor that the password
 for the next level is stored in a file called - located in the home 
directory. First we are again like the previous level going to confirm 
we are in home directory using the pwd command.

```bash
pwd
```

After the pwd command confirms we are in the home 
directory we need to list the contents of the directory to see whats 
there we do this using the ls command.

```bash
ls
```

From the ls command we can see there is a file called "-" 
in the home directory, so we are going to use the cat command to see the
 contents of this file.

```bash
cat ./-
```

From this command we have captured our flag for this level and obtained the password.

![bandit1-2.PNG](https://github.com/EoinReid/Bandit-OverTheWire/blob/main/bandit-screenshots/bandit1-2.png)

### Flag

```bash
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
```

### New Commands breakdown

```bash
cat ./-
```

As the filename we are trying to use the cat command for 
is called '-' we must be careful as bash will see this '-' as a synonym 
for stdin or standard input to get around this we added the prefix "./" 
to specify the current directory to differentiate between "-" meaning 
stdin and a filename c

# Level 2 → Level 3

### Level Goal

> The password for the next level is stored in a file called spaces in this filename located in the home directory
> 

### Walkthrough

We are told in the level goal descriptor that the password
 for the next level is stored in a file called spaces in this filename 
in the home directory.

```bash
pwd
```

After the pwd command confirms we are in the home 
directory we need to list the contents of the directory to see whats 
there we do this using the ls command.

```bash
ls
```

From the ls command we can see there is a file called 
spaces in this filename in the home directory, so we are going to use 
the cat command to see the contents of this file.

```bash
cat "spaces in this filename"
```

From this command we have captured our flag for this level and obtained the password.

![bandit2-1.png](https://github.com/EoinReid/Bandit-OverTheWire/blob/main/bandit-screenshots/bandit2-1.png)

### Flag

```bash
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
```

After capturing our flag we are going to move to the next level, which is called bandit3.


Enter the flag from above when prompted for the password for the next level.

### New Commands breakdown

```bash
cat "spaces in this filename"
```

As the filename we are trying to use the cat command for is called "spaces in this filename" if we try to use the command

```bash
cat spaces in this filename
```

we will get the errors

```bash
cat: spaces: No such file or directory
cat: in: No such file or directory
cat:  this: No such file or directory
cat: filename: No such file or directory
```

This is due to bash reading the spaces in between each 
other as seperate filenames instead of the name of one file with spaces 
in its name, to get around this we can add "" or '' quotation marks to 
specify it is a file of one name with spaces in the name.


# Level 3 → Level 4

### Level Goal

> The password for the next level is stored in a hidden file in the inhere directory.
> 

### Walkthrough

```bash
ls
```

From the ls command we can see there is another directory 
called "inhere", this is the directory the level goal specified so we 
are going to change to that directory.

```bash
cd inhere
```

Changing to the inhere directory.

```bash
ls -a
```

As the level goal descriptor specified a "hidden" file, we
 are going to use the ls command in this directory with the -a attribute
 so that it lists all contents in this directory even hidden files.
 
```bash
cat .hidden
```
From the ls -a command we found a hidden file called 
.hidden, so we are going to use the cat command to print its contents to
 the terminal.

![bandit3-1.png](https://github.com/EoinReid/Bandit-OverTheWire/blob/main/bandit-screenshots/bandit3-1.png)
### Flag

```
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

```

After capturing our flag we are going to move to the next level, which is called bandit4.

Enter the flag from above when prompted for the password for the next level.

### Commands breakdown

```
ls -a

```

Filenames that start with a "." are hidden from the 
directory, so using a normal ls command would turn up no results. Using 
the -a attritbute with the ls command allows you to see all files in a 
directory inlucding hidden files beginnging with "."

# Level 4 → Level 5

### Level Goal

> The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.
> 

### Walkthrough

```bash
ls
```

From the ls command we can see there is another directory 
called "inhere", this is the directory the level goal specified so we 
are going to change to that directory.

```bash
cd inhere
```

Changing to the inhere directory.

```bash
ls -l
```

As the level goal descriptor says human-readable file I 
used the -l attribute with the ls command to list the contents of the 
directory in a long format to see if it would give us some more useful 
information.

```bash
cat ./*
```

From the ls -l command we were able to learn that the 
files are all of the same type, so the quickest way to see the contents 
of all the files at once is using the cat command with ./* which will 
print all the contents of all the files in this directory to the 
terminal instead of having to cat each file manually.

```bash
cat ./-file07
```

Due to the output of printing all of the files together made it difficult to see what part of the output was the flag and what was garbage we are going to have to cat an individual file to see. The flag looks like its one of the last few files so we are going to cat this file and check its output and get the flag.

![bandit4-1.png](https://github.com/EoinReid/Bandit-OverTheWire/blob/main/bandit-screenshots/bandit4-1.png)

### Flag

```
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

```

After capturing our flag we are going to move to the next level, which is called bandit5.


Enter the flag from above when prompted for the password for the next level.

### New Commands breakdown

```
ls -l

```

l for long, this shows a detailed list of files in a long format. This will show you detailed information, starting from the
left: file permissions, number of links, owner name, owner group, file
size, timestamp of last modification, and file/directory name.

# Level 5 → Level 6

### Level Goal

> The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties: * human-readable * 1033 bytes in size * not executable
> 

### Walkthrough

```bash
ls
```

From the ls command we can see there is another directory 
called "inhere", this is the directory the level goal specified so we 
are going to change to that directory.

```bash
cd inhere
```

Changing to the inhere directory.

```bash
ls
```

I used the ls command to get a bearing on what is within 
the inhere directory this time, and from it we can see an array of 
different maybehere directories.

```bash
find -size 1033c
```

As the level goal descriptor says the file size is 1033 
bytes, we can use the find command to search for a file in this 
directory that is 1033 bytes in size, using the -size attribute and 
appending c to the end of 1033 to specify to the terminal we are looking
 for 1033 bytes.

```bash
cat ./maybehere07/.file2
```

From the find command the terminal returned the file and 
location "./maybehere07/.file2", so I then used the cat command to print
 its contents to the terminal.
 
 ![bandit5-1.png](https://github.com/EoinReid/Bandit-OverTheWire/blob/main/bandit-screenshots/bandit5-1.png)

### Flag

```
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

```

After capturing our flag we are going to move to the next level, which is called bandit6.

Enter the flag from above when prompted for the password for the next level.

### Commands breakdown

```bash
find -size 1033c
```

The find command is heplful for finding a specific file 
that you don't know the location of. In the find command we used in this
 walkthrough we used the -size attribute to specify we are looking for a
 file of a particular size, in this case 1033 bytes, we then wrote the 
size 1033 and added a c to specify it is 1033 bytes in size.

# Level 6  → Level 7

### Level Goal

> TThe password for the next level is stored somewhere on the server and has all of the following properties:
    owned by user bandit7
    owned by group bandit6
    33 bytes in size
> 

### Walkthrough

```bash
find / -user bandit7 -size 33c -group bandit6
```
The level goal states that the password is stored "somewhere on the server" this indicates that we are going to need to search not just our current directory but search from the root diretory (/) so we can the entire server for the flag. The level goal also gives us a few more hints about the files attributes that we can add to our command to narrow our search, such as the user owner of the file is bandit7, the size of the file is 33 bytes and the group owner of the file is bandit6.

![bandit6-1.PNG](https://github.com/EoinReid/Bandit-OverTheWire/blob/main/bandit-screenshots/bandit6-1.png)

After running this command we can see that the output isn't as clean as we would like, and there seem to be alot of garbage files that also match the same attributes as our flag. However all of these files seem to be returning an error of sorts, such as "permission denied" or "no such file or directory". Lucky for us we can add a little bit to our command and strip all these errors from the output.

```bash
find / -user bandit7 -size 33c -group bandit6 2>/dev/null
```

![bandit6-2.PNG](https://github.com/EoinReid/Bandit-OverTheWire/blob/main/bandit-screenshots/bandit6-2.png)

That's more like it! And now we can use the cat command to read the outputs of this file and get our flag!

### Flag

```
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

```

### New Commands breakdown

```
find / -user bandit7 -size 33c -group bandit6 2>/dev/null

```
As explained in the previous level we can use the find command to find a specific file that we do not know the location of according to file attributes we can specify in the command.

the "/" specifies that we want to start our search from the root folder (As opposed to from our current directory) this way we can ensure we search the entire server and aren't at risk of missing somewhere.

"-user bandit7 -size33c -group bandit6" specifies that we want to search for a file that is owned by a user bandit7, is a size of 33 bytes, and is owned by a group bandit6.

"2>/dev/null" was used to remove all those errors from the output so we could clear out the garbage and get to just the good stuff, such as our flag. But how does this work? The > opperator is used to redirect standard output, we can add a 2 in front like "2>" to redirect stderr or simply errors from the output of our command. Now we need somewhere to redirect that output to. /dev/null is the null device it takes any input you want and throws it away. It can be used to suppress any output.


# Level 7  → Level 8

### Level Goal

> The password for the next level is stored in the file data.txt next to the word millionth


### Walkthrough

For this level we know the password is in a file called data.txt, and that it is next to the word millionth. This means we just need to search data.txt for the word millionth using grep.

```bash
cat data.txt | grep "millionth"
```

And we get our flag!

![bandit7-1.PNG](https://github.com/EoinReid/Bandit-OverTheWire/blob/main/bandit-screenshots/bandit7-1.png)


### Flag

```
TESKZC0XvTetK0S9xNwm25STk5iWrBvP

```

### Commands breakdown


```bash
cat data.txt | grep "millionth"
```

For this command we used a concept we havent covered before in this CTF called "piping" denoted by the "|" symbol. Piping lets you take the output of one command (in this case cat data.txt) and use that output as the input for our next command, which is "grep".

grep lets us search files for a particular expression, such as "millionth".

So in summary, this command lets us read the contents of data.txt, and then search those contents for the word "millionth" so we can find our flag as the level goal explain it was beside this word in the file.

