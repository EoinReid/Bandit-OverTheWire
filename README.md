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

