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
- [Level 8 → Level 9](#level-8--level-9)
- [Level 9 → Level 10](#level-9---level-10)
- [Level 10 → Level 11](#level-10---level-11)
- [Level 11 → Level 12](#level-11---level-12)
- [Level 12 → Level 13](#level-12---level-13)
- [Level 13 → Level 14](#level-13---level-14)
- [Level 14 → Level 15](#level-14---level-15)
- [Level 15 → Level 16](#level-15---level-16)
- [Level 16 → Level 17](#level-16---level-17)
- [Level 17 → Level 18](#level-17---level-18)
- [Level 18 → Level 19](#level-18---level-19)
- [Level 19 → Level 20](#level-19---level-20)
- [Level 20 → Level 21](#level-20---level-21)
- [Level 21 → Level 22](#level-21---level-22)
- [Level 22 → Level 23](#level-22---level-23)
- [Level 23 → Level 24](#level-23---level-24)
- [Level 24 → Level 25](#level-24---level-25)
- [Level 25 → Level 26](#level-25---level-26)
- [Level 26 → Level 27](#level-26---level-27)
- [Level 27 → Level 28](#level-27---level-28)
- [Level 28 → Level 29](#level-28--level-29)
- [Level 29 → Level 30](#level-29--level-30)
- [Level 30 → Level 31](#level-30--level-31)
- [Level 31 → Level 32](#level-31--level-32)
- [Level 32 → Level 33](#level-32--level-33)

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

For this level we know the password is in a file called data.txt, and that it is next to the word millionth. 

```bash
ls
```

First we are juts confirming that data.txt is in our current directory.


```bash
cat data.txt | grep "millionth"
```
Then we just need to search data.txt for the word millionth using grep.

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

# Level 8 → Level 9

### Level Goal

> The password for the next level is stored in the file data.txt and is the only line of text that occurs only once
> 
### Walkthrough

So the level goal lets us know our flag is stored in a file called data.txt, and that it is the only line of text that occurs once. Whats another word for something that only occurs once? Unique. So we are going to be using the Uniq command here.


```bash
ls
```

First we are juts confirming that data.txt is in our current directory.


```bash
sort data.txt | uniq -u
```

Then we are going to sort data.txt and pipe the output to the uniq command to search for unique values in the file. The reason why we needed to sort this file first will be explained in the command breakdown section.

Now we have our flag!

![bandit8-1.PNG](https://github.com/EoinReid/Bandit-OverTheWire/blob/main/bandit-screenshots/bandit8-1.png)



### Flag

```
EN632PlfYiZbn3PhVK3XOGSlNInNE00t

```

### Commands breakdown

```bash
sort data.txt | uniq -u
```
So you might be wondering why we had to sort data.txt before using our uniq command. The Uniq command allows you to remove duplicates from a file get the unique values in the file. Unfortunately, uniq does not detect duplicate lines unless they are adjacent to each other in the file. So to work around this we first sort the data.txt file to ensure that all duplicate values will be adjcaent to each other in the file before we use our uniq command to remove them.

# Level 9  → Level 10

### Level Goal

>The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

### Walkthrough

The level goal tells us our flag is in the file data.txt, that it is a human-readable string in the file, and it has several = symbols before it.


```bash
ls
```

First we are juts confirming that data.txt is in our current directory.


```bash
strings data.txt | grep "="
```
As we know that the flag is a string, and preceed by "=" we are going to first get all the strings from the data.txt file and then pipe to grep to search those strings for an "=" symbol.

And we found our flag!


![bandit9-1.PNG](https://github.com/EoinReid/Bandit-OverTheWire/blob/main/bandit-screenshots/bandit9-1.png)

### Flag

```
G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

```

### Commands breakdown

```bash
strings data.txt | grep "="
```

The string command lets us take any printable (aka human readable) string from a file . We then pipe to grep to search through these human readable stings for any string that begins with an = symbol.

# Level 10  → Level 11

### Level Goal

> The password for the next level is stored in the file data.txt, which contains base64 encoded data

### Walkthrough

The level goal tells us that the flag is stored in the file data.txt, in base64 encoded data. This means to get our flag we have to decode the file.

```bash
ls
```

First we are juts confirming that data.txt is in our current directory.

```bash
base64 -d data.txt
```

Then using the base64 command we are going to decode the file from base64.

And we have our flag!

![bandit10-1.PNG](https://github.com/EoinReid/Bandit-OverTheWire/blob/main/bandit-screenshots/bandit10-1.png)


### Flag

```
6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

```

### Commands breakdown

```bash
base64 -d data.txt
```

The base64 command is used to encode or decode data to/from the base64 format. We can specify we want to decode from base64 using the -d flag in our command followed by the file we want to decode.

# Level 11  → Level 12

### Level Goal

> The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

### Walkthrough

The level goal tells us that our flag is stored in a file called data.txt where all letters have been rotated by 13 positions (aka by 13 letters).
This is known as the ROT13 algorithm and is a simple caeser cipher. For example using this algorithm the letter A because the letter N, as the letter N Is 13 letters away from A, the letter B would become the letter O and so on. So we just need to reverse this rotation by 13 to find out flag.


```bash
ls
```

First we are juts confirming that data.txt is in our current directory.

```bash
cat data.txt | tr '[a-z][A-Z]' '[n-za-m][N-ZA-M]'
```

Then we are going to output the contents of data.txt and pipe to the translate command where we are going to reverse the rotation by 13 letters to get the original text, and our flag!

![bandit11-1.PNG](https://github.com/EoinReid/Bandit-OverTheWire/blob/main/bandit-screenshots/bandit11-1.png)



### Flag

```
JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

```

### Commands breakdown

```bash
cat data.txt | tr '[a-z][A-Z]' '[n-za-m][N-ZA-M]'
```

In this command we are outputing the contents of data.txt file using cat, then we are piping to use the translate command. Translate (tr) is used to translate or delete characters from the stanard input, in this case the stdin is the contents of the data.txt file.

Then to reverse the ROT13 algorithm we are going to give our two sets in our tr command, the first set contain the normal alphabet range in both lower case and upper case and then in our second set the ROT13 alphabet range in lower case and uppercase.

Remember how above I explained how the ROT13 algorithm just shifts letters by 13, so A becomes N, B becomes O and Z becomes M? Well thats all we are specifing in our second set, and thats why in the second set a and A becomes n and N etc.

# Level 12  → Level 13

### Level Goal

> The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)

### Walkthrough


```bash
ls
```

First we ls to see if data.txt is in our current working directory. The level goal suggest we create a directory in /tmp to work out of so we are going to do that.


```bash
mkdir /tmp/eoin
```

Then we are going to copy data.txt from our current directory to /tmp/eoin and then change directory

```bash
cp data.txt /tmp/eoin
cd /tmp/eoin
```


We are going to use cat to take a look at the contents of data.txt
```bash
cat data.txt
```

AS the level goal told us - data.txt is a hexdump of a file, so we are going to need to reverse the hexdump back to a binary file by outputing the contents of data.txt and then using the xxd command to reverse the hexdump and redirect the output to a new file called data

![bandit12-1.PNG](https://github.com/EoinReid/Bandit-OverTheWire/blob/main/bandit-screenshots/bandit12-1.png)

```bash
cat data.txt | xxd -r >data
```

Now if we use the file command on the data file we can see that it is a gunzip compressed file.


```bash
file data
```

However, despite this being the files type it does not have a .gz file extension and as a result using gunzip (gz) to decompress the file will not work, so first we need to add on the .gz file exentesion to the file using the mv command and rename the file to data2 to keep track of our new file.

```bash
mv data data2.gz
```

then we will use the gunzip decompress command to decompress the data file.

```bash
gz -d data.gz
```

Now if we use file on data2 we will see that it is now a bzip2 file, so we are going to repeat the same process above except instead of gunzip, it is bzip2.

```bash
file data2
mv data2 data3.bz2
bzip2 -d data3.bz2
```

Now if we use file on data3 we will see that dat3 is a gz file, so we are going to do the same as what we did with the data file.

```bash
file data3
mv data3 data4.gz
gz -d data4.gz
```

If we use file on data4.bin we will see it is a tar file, so we are going to do similar to the above expect using tar instead of gz or bzip2.

```bash
file data4
mv data4 data5.tar
tar data5.tar
```

using file again we see that data5.bin is also a tar file so we will repeat the process.


```bash
file data5.bin
mv data5.bin data6.bin.tar
tar data6.bin.tar
```

Repeating the process again we see that data6.bin is a bz2 file so we will do the same process that we used with data2.

```bash
file data6.bin
mv data6.bin data7.bin.bz2
bzip2 -d data7.bin.bz2
```

Using file again we will see that data7 is a tar file so we will repeat the process for tar files we used previously.

```bash
file data7.bin
mv data7.bin data8.bin.tar
tar -xvf data8.bin.tar
```

Using file again we see that data8 is a gz file so we will repeat the process for gz files we used previously.

```bash
file data8.bin
mv data8.bin data9.bin.gz
gzip -d data9.bin.gz
```

And... using file on data9.bin and we see it is an ASCII text file hurrah!

use cat on data9.bin and we get our flag!


```bash
file data9.bin
cat data9.bin
```

![bandit12-2.PNG](https://github.com/EoinReid/Bandit-OverTheWire/blob/main/bandit-screenshots/bandit12-2.png)

### Flag

```
wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw

```

### Commands breakdown


```bash
mkdir /tmp/eoin
```

the /tmp directory is a directory that works similar to your RAM, its a directory you use when you only want the contents to stay for as long as your PC as on, once your PC turns off or reboots anything in /tmp will be lost, same as anything in your computers memory (RAM). So this allows us to work in a directory without messing up other directories on the system and without having to worry about cleanig up the contents afterwards.

```bash
cp data.txt /tmp/eoin
```

the cp or copy command allows us to copy a file to another location, the same as you would when you right click and click copy and then right click and click paste. It will not remove or delete the orignal file.

```bash
cat data.txt | xxd -r >data
```
In this command we used cat to output the contents of data.txt, which was a hashdump. The command used to both create a hashdump of a file, and reverse a hexdump back to its original binary is xxd. so we are going to use this with the -r flag (reverse) to reverse the hashdump file back to its binary form and redrirect the output to a new file called data so we will still have data.txt to work with if anything goes wrong with our new file.


```bash
file data
```
As the level goal mentioned that the files were repeatdly compressed we are going to check the file type of data now that it is back in its binary format. This command told us that data was a file of type gzip, which is a compressed file type, just like our level goal hinted us about.

```bash
mv data data2.gz
```
As we know that the data file is a gzip file we know that we are going to need to use the gzip command (gz) to decompress the file. However this command only works on files that have the .gz extension. So we know that data is a gzip file, but it doesnt have the .gz extension so what gives? we cant decompress? Well this is where the mv or move command comes in. We can just rename the data file to have the .gz extension like the gzip command expects and it will work!

This process it the same for the bz2 and tar files in this level, where the command will expect a particular file extension in order to decompress the file, so we can just rename the files with mv.

```bash
gz -d data2.gz
```
To decompress our newly named data2.gz file we can use the gz command with the -d (for decompress) flag.


```bash
bzip2 -d data3.bz2
```
Like with the gz command, to decompress a bz2 file we will have to use the bzip2 command with the -d flag (for decompress)


```bash
tar -xvf data8.bin.tar
```
Similar with gz and bz2 for .tar files we can use the tar command to decompress or extract the contents. We used the -xvf flags so lets break them up. -x is for extracting the files, -v means verbosely or in other words just show more information about what the command is doing in the terminal, and -f is for file so you can specify the file you want to use with tar.

# Level 13  → Level 14

### Level Goal

> The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Note: localhost is a hostname that refers to the machine you are working on

### Walkthrough

After logging into bandit13, we are going to have a look at the directory contents.

```bash
ls
```

The level goal mentions that we will need a private SSH key in order to log on to the next level, and we can see that there is a file called sshkey.private in our directory. Let's use cat to see what's inside

```bash
cat sshkey.private
```

Looks like a private sshkey to me! 


![bandit13-1.PNG](https://github.com/EoinReid/Bandit-OverTheWire/blob/main/bandit-screenshots/bandit13-1.png)


```bash
ssh -i sshkey.private -p 2220 bandit14@localhost -i sshkey.private
```
WE can use this ssh private key to log into bandit14 without using a password. 

The level goal mentioned that the flag would be stored in /etc/bandit_pass/bandit14 so lets use cat to get the contents of this.

```bash
cat /etc/bandit_pass/bandit14 
```
and we have our flag!

![bandit13-2.PNG](https://github.com/EoinReid/Bandit-OverTheWire/blob/main/bandit-screenshots/bandit13-2.png)

### Flag

```
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq

```

### Commands breakdown

```bash
ssh -i sshkey.private -p 2220 bandit14@localhost -i sshkey.private
```
In the past using ssh we have only used the -p flag along with specifing the username and the host address, then we are usally prompted for a password (the previous levels flag). However if you have a private key the provides ssh access you can use this in place of a password to prove you have the correct authorisation. Thats what the -i flag is for, you use the -i to say you are going to use an ssh key and provei the sshkey location/path.

The level goal mentioned connecting via localhost, so that is why we were able to just use bandit14@localhost instead of specifying the full host name as usual, because we are already on the host so localhost = bandit.labs.overthewire.org

# Level 14  → Level 15

### Level Goal

>The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.

### Walkthrough

The level goals states that we need to submit the password of bandit14, which we got from the previous level from /etc/bandit_pass/bandit14 (fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq), to port 3000 on localhost. We are going to use the netcat command for this.

```bash
nc localhost 30000
```
Then we can just enter our password and we will get our new flag back!

![bandit14-1.PNG](https://github.com/EoinReid/Bandit-OverTheWire/blob/main/bandit-screenshots/bandit14-1.png)

### Flag

```
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

```

### Commands breakdown

```bash
nc localhost 30000
```

Netcat, or nc, is a command that lets you read or write data between two networks. Using nc here we are connecting to localhost (aka the current host we rae connected to) and specifiying port 30000 from the level goal.


# Level 15  → Level 16

### Level Goal

> The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL encryption.

### Walkthrough

The level goal says to submit the password we used to get into the current level (jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt) to local host port 30000 over SSL, so we are going to use the openssl command.

```bash
openssl s_client -connect localhost:30001 
```

Then we are going to submit the password.

and we have our flag!


![bandit15-1.PNG](https://github.com/EoinReid/Bandit-OverTheWire/blob/main/bandit-screenshots/bandit15-1.png)
![bandit15-2.PNG](https://github.com/EoinReid/Bandit-OverTheWire/blob/main/bandit-screenshots/bandit15-2.png)



### Flag

```
JQttfApK4SeyHwDlI9SXGR50qclOAil1

```

### Commands breakdown


```bash
openssl s_client -connect localhost:30001 
```
openssl s_client -connect, allows you to connect to the host over TLS/SSL and to provide input to the host, in our case the host was localhost and the port was 30001

# Level 16  → Level 17

### Level Goal

> The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

### Walkthrough

The level goals tells us that the port we need to submit the password to is in the port range 31000 to 32000 so we are going to conduct an nmap scan on localhost in this port range to to see which ports are open in this range and which have SSL.


```bash
nmap localhost -p31000-32000 -A
```

![bandit16-1.PNG](https://github.com/EoinReid/Bandit-OverTheWire/blob/main/bandit-screenshots/bandit16-1.png)

We can see in the screenshot that there are 5 open ports, of which only 2 speak SSL, and only one does not have an echo service (Meaning that it will not just repeat back what we send to it as the level goal warns). So it looks like port 31790/tcp is our target port so lets test it out using openssl.


```bash
openssl s_client -connect localhost:31790
```

![bandit16-2.PNG](https://github.com/EoinReid/Bandit-OverTheWire/blob/main/bandit-screenshots/bandit16-2.png)

And lets enter our password we used to get into this level(JQttfApK4SeyHwDlI9SXGR50qclOAil1) and we have our flag, which is an RSA private key.

![bandit16-3.PNG](https://github.com/EoinReid/Bandit-OverTheWire/blob/main/bandit-screenshots/bandit16-3.png)

We are going to copy this RSA key and paste it into a file on our computer, I am doing this use the nano command to create a new file and paste it in and saving it as bandit17.sshkey

```bash
nano
```

![bandit16-4.PNG](https://github.com/EoinReid/Bandit-OverTheWire/blob/main/bandit-screenshots/bandit16-4.png)

im then going to change the permissions of the file with chmod so we can use it to SSH Into bandit17

```bash
chmod 600 bandit17.sshkey
```


```bash
ssh -i bandit17.sshkey -p 2220 bandit17.bandit.labs.overthewire.org
```

### Flag

```
This levels Flag is the RSA private key that is returned from the server.

```

### Commands breakdown


```bash
nmap localhost -p31000-32000 -A
```
In this command we are using the nmap tool, which allows us to scan a host to find out things such as any open ports they have, in this case that host is local host, nmap by default will scan a host for the 1000 most common port services so we are going to specify which ports in particular we want to scan as the level goal specifies this port range using the -p flag. I also used the -A flag which enable OS detection, version detection, script scanning, and traceroute and will allow us to see what services are running on each port. Without using the -A flag we would have to individually test each port using openssl to find which ports are using ssl and of those which are the correct port so -A speeds things up for us.

```bash
chmod 600 bandit17.sshkey
```
chmod is used to change the permissions of a file, 600 is a shorthand way of writing permissions for three different types of people (user permissions)(group permissions)(everyone else), 6 in this case means we want the file owner to have read and write permissions and groups everyone else to have no permissions of our file. This is neccessary when using a private key to conenct over SSH as this key cannot be accessible by other people. If for example i set the permissions of bandit17.sshkey to 666 (meaning giving read and write permissions to everyone) and attempt to connect to bandit17 I will recieve the following error.

```bash
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@         WARNING: UNPROTECTED PRIVATE KEY FILE!          @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
Permissions 0666 for 'bandit17.sshkey' are too open.
It is required that your private key files are NOT accessible by others.
```

# Level 17  → Level 18

### Level Goal

> There are 2 files in the homedirectory: passwords.old and passwords.new. The password for the next level is in passwords.new and is the only line that has been changed between passwords.old and passwords.new

### Walkthrough

As the level goal states that the flag for th next level is in a file called passwords.new and is the only line that is different between passwords.old and passwords.new. So to find this new line (or different line you could say!) we are going to use the diff (different) command.

```bash
diff passwords.old passwords.new
```

And we have our flag!

![bandit17-1.PNG](https://github.com/EoinReid/Bandit-OverTheWire/blob/main/bandit-screenshots/bandit17-1.png)


### Flag

```
hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg

```

### Commands breakdown


```bash
diff passwords.old passwords.new
```
The diff command allows you to compare files line by line and fine the differences, if any, between them. In this case it allowed us to find the one line that was different between the two files, wihch was our flag.

# Level 18  → Level 19

### Level Goal

> The password for the next level is stored in a file readme in the homedirectory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.


### Walkthrough

As the level goal states that someone has edited the .bashrc file to log you out when you attempt to log in with SSH, that means to log in successfully we will have to log in in such a way that we can ignore the .bashrc file that is going to log us out, we can do this by telling bash to not use a profile or use the rc file on startup.

```bash
ssh bandit18@bandit.labs.overthewire.org -p 2220 "bash --noprofile --norc"
```

As we have told bash not to use a profile or the rc file, we have succesfully bypassed the edited bashrc file that will log us out, but as a result of doing so you will notice that your shell looks empty or like the log in has "hung", well this is because there is no settings being used, so you can just start typing your commands. First we want to see the contents of the directory we are in.


```bash
ls
```

the readme file looks interesting so lets print out its contents

```bash
cat readme
```

and we have our flag!

![bandit18-1.PNG](https://github.com/EoinReid/Bandit-OverTheWire/blob/main/bandit-screenshots/bandit18-1.png)


### Flag

```
awhqfNnAbc1naukrpqDYcF95h7HoMTrC

```

### Commands breakdown

```bash
ssh bandit18@bandit.labs.overthewire.org -p 2220 "bash --noprofile --norc"
```

The fist bit of this command is the normal ssh command we have used in the past, but the part in quoatation marks is new, and it is what we used to bypass the edited .bashrc file.

"bash --noprofile --norc" tells bash to disable processing the startup files and setting, which allows us to ignore the edited .bashrc file. One downside of this method is that this will also mean bash will not set PS1(the variable used to generate the terminal prompt that we are used to) and will make it look as though the terminal has hung, but this isn't such a big deal once you know to expect this.

# Level 19  → Level 20

### Level Goal

>To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

### Walkthrough

As the level goal states the we need to use the setuid binary file in our home directory lets check the contents of our current directory to see if it is there.

```bash
ls
```

We can see that there is a file called bandit20-do lets execute it and see how we can use it.

```bash
./bandit20-do
```

So we see that it lets us run a command as another user, well we know that the password for the next file is in the usual /etc/bandit_pass/ location so lets execute this file to attempt to output the contents of bandit20 in bandit_pass and try get our next flag!

```bash
./bandit20-do cat /etc/bandit_pass/bandit20
```

And we have our flag!

![bandit19-1.PNG](https://github.com/EoinReid/Bandit-OverTheWire/blob/main/bandit-screenshots/bandit19-1.png)


### Flag

```
VxCazJaVykI6W36BkBU0mJTCM8rR95XT

```

### Commands breakdown

```bash
./bandit20-do
```
To execute a file you want to put ./ before the name of the file

```bash
./bandit20-do cat /etc/bandit_pass/bandit20
```
Becuase bandit20-do has a SUID (set user identity) bit, it allows us to temporarily execute files/commands with the same permissions and privileges as the file owner. This is quite useful in alot of scenarios, such as when you want to update your accounts log in password, you will need temporarily elevated privileges (usually of root) to write your new password to the passwords database.

# Level 20  → Level 21

### Level Goal

>There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

### Walkthrough

In the level goal it lets us know there is an SUID binary in the home directory so we are going to find the file by listing the contents of the directory.

```bash
ls
```

We see there is a SUID binary file called suconnect so we are going to execute it so we can see its usage.

```bash
./suconnect
```

We can see that it connects to a give port on localhost and then if it recieves the correct password (that being the password for the current level) it will transmit back the password for the next level.

So we are going to use netcat to to provide the current password level on port 54321.

```bash
echo "VxCazJaVykI6W36BkBU0mJTCM8rR95XT" | nc -l -p 54321 &
```
Now we can use the suconnect binary on port 54321 to get the password for the next level

```bash
./suconnect 54321
```

and we have our flag!


![bandit20-1.PNG](https://github.com/EoinReid/Bandit-OverTheWire/blob/main/bandit-screenshots/bandit20-1.png)


### Flag

```
NvEJF7oVjkddltPSrdKEFOllh9V1IBcq

```

### Commands breakdown


```bash
echo "VxCazJaVykI6W36BkBU0mJTCM8rR95XT" | nc -l -p 54321 &
```
In this command we are echoing the password for the current level and then piping the output to the netcat (nc) command, using the -l flag to specify we are going to listen and -p to specify ove rport 54321. the & symbol is used to run this command in the background so we can continue to use our terminal while it runs.

# Level 21  → Level 22

### Level Goal

> A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

### Walkthrough

The level goal lets us know that we need ot look in /etc/cron.d/ so we are first going to charge our directory to that.

```bash
cd /etc/cron.d/
```
Next we are going to list the directory contents to have a look at whats there.

```bash
ls
```

We see that there is a file called cronjob_bandit22 that looks interesting so we are going to output the contents and see whats inside.

```bash
cat cronjob_bandit23
```

We can see from the output that the cronjob is always running (due to the * symbols) an that it is taking the outputs of a file called cronjob_bandit22.sh in /usr/bin/ and discarding it using /dev/null so we are going to take a look at this shell file.

```bash
cat /usr/bin/crojob_bandit22.sh
```

We can see that this shell script is changing the permissions of a file in the temp directory and taking the output of /etc/bandit_pass/bandit22 and redirecting this output to /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv. So to get the password for the next level we are going to need to read the contents of this tmp file.


```bash
cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
```

And we have our flag!

![bandit21-1.PNG](https://github.com/EoinReid/Bandit-OverTheWire/blob/main/bandit-screenshots/bandit21-1.png)

### Flag

```
WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff

```

### Commands breakdown

No new commands in this level.


# Level 22  → Level 23

### Level Goal
> A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

### Walkthrough

In the level goal we see that we need to look in /etc/cron.d/ again so we are going to change our directory.

```bash
cd /etc/cron.d/
```

Next we are going to list the contents of our directory 

```bash
ls
```

We can see there is an interesting file called cronjob_bandit23 so we are going to output the contents of this file to see whats inside.

```bash
cat cronjob_bandit23
```
we can see that this cronjob, similar to the previous level, is running all the time (due to the * symbols) and that it is redirecting the output of a shell script called /usr/bin/cronjob_bandit23.sh to /dev/null to be discarded. So we are going to take a look at the shell script.

```bash
cat /usr/bin/cronjob_bandit23.sh
```

We can see in the shell script that there is two variables, one is myname which is equal to the current logged in user and mytarget which is equal to the phrase "echo I am user $myname | md5um | cut -d ' ' -f 1". The password file we are looking for is located in /tmp/$mytarget.

For myname we know that we want that to be bandit23, as that would be the result if we ran whoami on bandit23 user. so we can calcluate mytarget but replaced $myname with the value bandit23 and running the command from the shell script in our terminal to get the required hash name.

```bash
echo I am user bandit23 | md5sum | cut -d ' ' -f 1
```

From this we get the hash we need and the file name so we can just output the contents


```bash
cat /tmp/8ca319486bfbbc3663ea0fbe81326349
QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
```

And we have our flag!

![bandit22-1.PNG](https://github.com/EoinReid/Bandit-OverTheWire/blob/main/bandit-screenshots/bandit22-1.png)

### Flag

```
QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G

```

### Commands breakdown

```bash
echo I am user bandit23 | md5sum | cut -d ' ' -f 1
```
This command is taking from the shell script cronjob_bandit23.sh. First we are echoing "I am user bandit23" and then piping this output to the md5sum command which will calculate an md5 hash of this output. We then pipe this has to the cut command, where we are going to specify the delimiter as ' '  ( a space) using the -d flag and that we want the first field using -f 1 (cut takes inputs as a list starting at index 1, so our hash will be a single entry in the list so thats why we need to specify 1, if you change this command to -f 2 for example the output will be blank).

# Level 23  → Level 24

### Level Goal

> A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

### Walkthrough

The level goal tells us to look in /etc/cron.d/ so we are going to change directories.

```bash
cd /etc/cron.d/
```

Then we are going to read the outputs of cronjob_bandit24.sh similar to previous levels involving /etc/cron.d


```bash
cat cronjob_bandit24
```

We see this cron file is mentioning a script in the /usr/bin directory so we are going to take a look at this script.


```bash
cat /usr/bin/cronjob_bandit24.sh
```


```bash
bandit23@bandit:/etc/cron.d$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done
```

We can see in the script that every 60 seconds it is executing all scripts in /var/spool/$myname/foo and then deleting them. 

Let's try to just print the output of /etc/bandit_pass/bandit24]

```bash
cat /etc/bandit_pass/bandit25
```

```bash
Output:
cat: /etc/bandit_pass/bandit24: Permission denied

```

yeah.. that would be too easy, but we have another way! using /var/spool/myname/foo and placing a script in there to read the password for us..

Lets start by creating a directory in /tmp we can work from


```bash
mkdir /tmp/shell-temp
```

Then we need to create our shellscript file

```bash
touch shellscript.sh
```

Then we need to change the permissions so everyone has read,write and executable permissions


```bash
chmod 777 shellscript.sh
```

And let write to our script using nano


```bash
nano shellscript.sh
```

What we are going to do is attempt to exploit how scripts are ran in /var/spool/$myname/foo by trying to output the bandit24 password and writing it to a file in our tmp directory

add the following line to your shell script


```bash
#! /bin/bash
cat /etc/bandit_pass/bandit25 > /tmp/shell-temp/password
```

save and exit.

Now we need to create the password file that this script is going to write to


```bash
touch password
```

And lets update the file permissions so that anyone can read and write to the file


```bash
chmod 666 password
```

now we just need to copy of shell script into /var/spool/bandit24/foo and wait 60 seconds for it to run


```bash
cp shellscript.sh /var/spool/bandit24/foo
```

we can use the ls command to check the timestamp of the files in our directory and wait for password to be modified once it has been use cat to read the contents


```bash
ls -la
```

```bash
cat password
```

And we have our flag!


### Flag

```
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar

```

### Commands breakdown

No new commands in this level!

# Level 24  → Level 25

### Level Goal

> A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.
You do not need to create new connections each time

### Walkthrough

The level goal lets us know we are going to have to write a shell script to brute force our way into getting the password this time, so lets make a directory in /tmp to work from and change our directories

```bash
mkdir /tmp/shell-script
cd /tmp/shell-script
```

Then lets use nano to create our shell script

```bash
nano brute-force.sh
```

So we now from the level goal our script needs to do a couple things.

1) Connect to port 30002 on localhost
2) Provide the password for bandit24 along with a 4 digit pincode (10,000 possible combinations due to there 10 options per digit (0-9) and there being 4 digits, so 10^4).
3) No need to create a new connection everytime

So lets write our shell script

```bash
#! /bin/bash
for i in {0000..9999}
do 
  echo "VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar $i"
done | nc localhost 30002
```

Then run our script

```bash
bash brute-force.sh
```

And we get our flag!

### Flag

```
p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d

```

### Commands breakdown

```bash
#! /bin/bash
for i in {0000..9999}
do 
  echo "VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar $i"
done | nc localhost 30002
```

I am going to breakdown our shell script so you understand what we did and how we got our flag using it.

```bash
for i in {0000..9999}
```
This is a for loop that is set in the range 0000-9999. This means that our loop will run 10,000 times start ing at 0000. and "i" will be assigned a new number depending on what iteration of the loop it is in. For example on the first iteration i = 0000, the second iteration i = 0001 and so on.

```bash
do
 echo "VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar $i"
 done | nc localhost 30002
```

In the last part of the script we are echoing the bandit24 password and $i (which is equal to i as explainaed above) so for example in the first iteration we will be echoing "VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar 0000". Then we are using the done keyword and piping to netcat to connect to localhost over port 30002, this allows us to try this using a continuos connection so we dont have to reconnect everytime we attempt to brute force speeding up the process.

# Level 25  → Level 26

### Level Goal

> Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not /bin/bash, but something else. Find out what it is, how it works and how to break out of it.

### Walkthrough

We are first going to take a look at our directory contents

```bash
ls
```

We see there is a file called bandt26.sshkey lets try to ssh into bandit26 with it.

```bash
ssh -i bandit26.sshkey bandit26@localhost -p 2220
```

You can see that initally we connect, but then we are disconnected from ssh-ing in as bandit26 using this key. This looks like a similar issue to one of the previous levels were the .bashrc file was configured to disconnect us. In the level goal it states that the shell for bandit26 is different than /bin/bash so lets try find out what it is.


We are going to look in the passwd file for bandit26

```bash
cat /etc/passwd | grep "bandit26"
```

We can see the shell bandit26 is using is /usr/bin/showtext

```bash
Output:
bandit26:x:11026:11026:bandit level 26:/home/bandit26:/usr/bin/showtext
```
Lets take a look at it

```bash
cat /usr/bin/showtext
```
We can see that it is actually a shell script, and it is the reason it is causing us to be disconnected as it displaying the usual welcome ssh screen and then exiting.


```bash
output:
#!/bin/sh

export TERM=linux

exec more ~/text.txt
exit 0

```
What this means instead of receiving the actual welcome graphic we are used to, the display from the text.txt file is being displayed using the more command and then exited, which may work to our advantage.

lets try making our terminal smaller and logging in with ssh again.

You will know you will have done this right when you see the "more" popup on the lower left hand side of your terminal like the screesnhot below.

![Screenshot from 2022-12-20 17-56-26](https://user-images.githubusercontent.com/40269943/208734193-5928c40f-c1dc-4e7b-8d1e-eea927f031f7.png)

Next you want to press the "v" key, this will actually allow you to edit the text.txt file that is being displayed.

Then in vim, you want to enter ":e /etc/bandit_pass/bandit26"

And we have our flag!

![Screenshot from 2022-12-20 17-58-54](https://user-images.githubusercontent.com/40269943/208734531-97f2e635-07a4-4454-8fee-dc7894bb118e.png)


### Flag

```
c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1

```

### Commands breakdown

No new commands in this level

# Level 26  → Level 27

### Level Goal

> Good job getting a shell! Now hurry and grab the password for bandit27!

### Walkthrough

To get started we need to pick up where we left off on Level 25, inside vim editing the text.txt file that we accessed using the more exploit.

From there we are going to get access to the bandit27 shell.

First we are going to reset the shell to /bin/bash

```bash
:set shell=/bin/bash
```
Then we are going to access the shell
```bash
:shell
```
We now have access to bandit26's shell, lets take a look at the directory

```bash
ls
```

We can see the text.txt file that contained the display ASCII art, as well as a file called bandit27-do, lets run it to see what it is

```bash
./bandit27-do 
Run a command as another user.
```
We can see that it allows us to run a command as another user, so lets use this to get the flag.


```bash
./bandit27-do cat /etc/bandit_pass/bandit27
```

And we have our flag!

### Flag

```
YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS

```

### Commands breakdown


```bash
:set shell=/bin/bash
```

In this command within vim, we are specifying that we want to set our shell as /bin/bash, aka the shell that we are normally using.

```bash
:shell
```
In this command within vim, we are telling vim to open up a shell.

# Level 27  → Level 28

### Level Goal

> There is a git repository at ssh://bandit27-git@localhost/home/bandit27-git/repo. The password for the user bandit27-git is the same as for the user bandit27.
Clone the repository and find the password for the next level.

### Walkthrough

First we are going to create a directory in /tmp to work from and change directories to it.
```bash
mkdir /tmp/git
cd /tmp/git
```
Then since the level goal tells us the location of the git repo we are going to use git clone to clone the repo.

```bash
git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo
```
When prompted for a password as stated in the level goal the password is the same as bandit27's.

YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS

Then lets change directory to inside the repo and look at the contents.

```bash
cd repo
ls
```

We see an interesting file called README so lets read it.

```bash
cat README
```

And we have our flag!

### Flag

```
AVanL161y9rsbcJIsFHuw35rjaOM19nR

```

### Commands breakdown

```bash
git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo
```
git clone allows you to copy the repository of given repo, in this instance we provided bandit27-git/repo path and made a copy of it to our current directory.


# Level 28 → Level 29

### Level Goal

> There is a git repository at ssh://bandit28-git@localhost/home/bandit28-git/repo. The password for the user bandit28-git is the same as for the user bandit28.
Clone the repository and find the password for the next level.

### Walkthrough

Like similar levels we are going to start by creating a directory in /tmp to work frome and change directories

```bash
mkdir /tmp/git-b28
cd /tmp/git-b28
```
Then we are going to clone the git repository using the repo location provided, remember the password for bandit28-git is the same as the password for bandit28.

```bash
git clone ssh://bandit28-git@localhost:2220/home/repo
```

Then we are going to look the directory contents and change directory to repo
```bash
ls
cd repo
```

We see a README.md file so lets take a look at the contents
```bash
cat README.md
```
README.md
```bash
 Bandit Notes
Some notes for level29 of bandit.

 credentials

- username: bandit29
- password: xxxxxxxxxx
```

We see that there is a username, but the password is censored out, lets take a look a the commit logs for this repo to see if it was maybe left in in an earlier version.

```bash
git log .
```
Git commit logs:
```bash
commit 5f45cfaca938393c7706fec16ab1ca627e947f64 (HEAD -> master, origin/master, origin/HEAD)
Author: Morla Porla <morla@overthewire.org>
Date:   Sat Dec 3 08:14:06 2022 +0000

    fix info leak

commit f08ee321c5f564b2da90789fac14b5ae2e55c56c
Author: Morla Porla <morla@overthewire.org>
Date:   Sat Dec 3 08:14:06 2022 +0000

    add missing data

commit 6968b2ffdcc317a1aeb2ebfb54259f860a390354
Author: Ben Dover <noone@overthewire.org>
Date:   Sat Dec 3 08:14:06 2022 +0000

    initial commit of README.md

```
We are currently in commit 5f45cfaca938393c7706fec16ab1ca627e947f64 (Where it says it fixed the info leak.. interesting) so lets checkout the previous commit f08ee321c5f564b2da90789fac14b5ae2e55c56c and try see what info was leaked

```bash
git checkout f08ee321c5f564b2da90789fac14b5ae2e55c56c
```

Now lets look at README.MD again
```bash
cat README.MD
```

And we have our flag!

### Flag

```
tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S

```

### Commands breakdown

```bash
git log .
```
This command allows us to see all commit logs for a git repository.

```bash
git checkout f08ee321c5f564b2da90789fac14b5ae2e55c56c
```
this command lets us "checkout" (like you would checkout something in a shop) a different commit, or version, of the repository.

# Level 29 → Level 30

### Level Goal

> There is a git repository at ssh://bandit29-git@localhost/home/bandit29-git/repo. The password for the user bandit29-git is the same as for the user bandit29.
Clone the repository and find the password for the next level.

### Walkthrough

Similar to previous levels lets create a directory in /tmp to work from and change directories to it.

```bash
mkdir /tmp/git-b29
cd /tmp/gitb29
```

Then lets clone the git repo from the level goal

```bash
git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo
```

And then we switch to the repo directory and look at the contents
```bash
cd repo
ls
```
Next, lets read the output of the readme file.
```bash
cat README.md
```
We can see there i a username, but the readme tells us that there is no password saved "in production", which reads to me that the passwords might be saved in the read me in non-production or testing branches.

```bash
bandit29@bandit:/tmp/git29/repo$ cat README.md 

# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: <no passwords in production!>
```
Lets take a look at the different branches of this repo.
```bash
git branch -r
```
We see a few different branches here, we are currently in origin/master, lets try switching to origin/dev to see if they left any credentials in their development branch.

```bash
bandit29@bandit:/tmp/git29/repo$ git branch -r
  origin/HEAD -> origin/master
  origin/dev
  origin/master
  origin/sploits-dev
```

Switch branches using git checkout then read the contents of the README.md for this branch.
```bash
git checkout origin/dev
cat README.md
```

And the credentials are left there so we have our flag!

### Flag

```
xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS

```

### Commands breakdown
No new commands in this level

# Level 30 → Level 31

### Level Goal

> There is a git repository at ssh://bandit30-git@localhost/home/bandit30-git/repo. The password for the user bandit30-git is the same as for the user bandit30.
Clone the repository and find the password for the next level.

### Walkthrough

Similar to previous levels we are going to create a directory in /tmp to work from and change directories to it.
```bash
mkdir /tmp/git-b30
cd /tmp/gitb30
```
Then we clone the git repo from the level goal
```bash
git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo
```
then change directories to repo and list the contents of the directory
```bash
cd repo
ls
```
Then lets read the contents of README.md
```bash
cat README.md
```
So it seems to be an empty file, lets check the commit history and look at branches to see if there is anything there we can use.
```bash
bandit30@bandit:/tmp/git-b30/repo$ cat README.md 
just an epmty file... muahaha
```

```bash
git branch -a
```
No other branches

```bash
git log .
```
No other commits

One thing we haven't tried before is looking the the tags, these are usually used to keep track of important versions.

```bash
git tag
```
We can see that there is actually a tag called secret, not suspicious at all.. Lets see what its inside

```bash
bandit30@bandit:/tmp/git-b30/repo$ git show secret
```

And we have our flag!

### Flag

```
OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt

```

### Commands breakdown

```bash
git tag
```
Tags in git are usually used as a reference to specific points in a git repositories history. It is usually used to mark important version releases.

```bash
bandit30@bandit:/tmp/git-b30/repo$ git show secret
```
git show is used to view expanded information and details about a git object, such as a tag in this case but can also be used with commits, trees and other git objects.

# Level 31 → Level 32

### Level Goal

> TThere is a git repository at ssh://bandit31-git@localhost/home/bandit31-git/repo. The password for the user bandit31-git is the same as for the user bandit31.
Clone the repository and find the password for the next level.

### Walkthrough

Similar to previous levels we are going to create a directory in /tmp to work from and change directories to it.
```bash
mkdir /tmp/git-b31
cd /tmp/gitb31
```

Then we are going to clone the git repo from the level goal
```bash
git clone ssh://bandit31-git@localhost:2220/home/bandit31-git/rep
```
Then switch directories to repo and list the contents
```bash
cd repo
ls -la
```

Are usual README.md there is there but also a .gitignore file that we haven't seen before.

Lets check the contents of the readme file.
```bash
cat README.md
```
We can see from the file that our goal for this level is to push a file this time, called key.txt with the text "May I come in?" to the master branch.

```bash
bandit31@bandit:/tmp/git-b31/repo$ cat README.md 
This time your task is to push a file to the remote repository.

Details:
    File name: key.txt
    Content: 'May I come in?'
    Branch: master

```

Lets create key.txt with the content.
```bash
echo "May I come in?" > key.txt
```

Next lets add key.txt to our git
```bash
git add key.txt
```
Uh oh, that .gitignore file is causing our key.txt file to be ignore.
```bash
The following paths are ignored by one of your .gitignore files:
key.txt
Use -f if you really want to add them.
```
lets see the contents of .gitignore
```bash
cat .gitignore
```
it ignores all .txt files!, lets edit it to change this and remove the "*.txt" line

```bash
nano .gitignore
```
Lets re-add our key.txt file
```bash
git add key.txt
```

Then lets create our git commit message
```bash
git commit -m "adds key.txt file"
```
And finally push to the master branch.
```bash
git push origin master
```

And we have our flag!

### Flag

```
rmCBvG56y58BXzv98yZGdO7ATVL5dW8y 

```

### Commands breakdown

```bash
git add key.txt
```
this command allows us to add a file to be included in git. Just because the file was in the repo directory doesn't automatically mean it will be captured but git.

```bash
git commit -m "adds key.txt file"
```
The git commit command allows us to commit and comment on any changes we have made to the repo.

```bash
git push origin master
```
git push then allows us to "push" our changes and commits to the branch, in this case our master branch.

# Level 32 → Level 33

### Level Goal

> After all this git stuff its time for another escape. Good luck!

### Walkthrough

So we log in and see that the shell doesn't seem to be our usual bash shell, lets try list the directory contents and see what happens.

```bash
ls
```
So it seems the shell is converting all our commands to uppercase causing them to be unrecognised.

Lets try invoke our usual bash shell using the $0 process

```bash
$0
```
And we have escaped the uppercase shell! Lets try see whats in the directory.

```bash
ls -la
```

Nothing too interesting so lets try print the password from the usual location
```bash
cat /etc/bandit_pass/bandit33
```

And we have our flag!

### Flag

```
odHo63fHiFqcWWJG9rLiLDtPm45KzUKy
```

### Commands breakdown

```bash
$0
```

