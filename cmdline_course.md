---
layout: default
---

### COMMAND-LINE COURSE

This course was an introduction to command-line tools for linguists.

#### Week 1: Introduction to Command-Line Environments

First week we looked at terminal and basic commands as well as different types of files.
I had used terminal before, so i was familiar with the basic commands such as wget, echo and mv. However, there were some new commands as well, for example that you can 
use dots to point to directories:
`..` means one directory above, so if you want to change to one directoty above, you can just use `cd ..`. Here are some other commands:  

| Command  | What it does            |
| -------- |:-----------------------:|
| ls       | list directory contents |
| cp       | copy                    |
| cd       | change directory        |
| mkdir    | make directory          |  

I was not familiar with different types of files, I learned about text and binary files and their differences. I had not used text editors before so using nano was new to 
me.

#### Week 2: Navigating a UNIX System

On week 2 we learned about thhe UNIX file system, permissions and processes. All of this was new to me. I learned about the root user, which is a user in UNIX that can 
do basically anything and you might need to switch to root used to execute some commands. You can also change the permissions of some files with chmod. For example, if 
you want to give only read rights to only the owner of a file you could use the command 
```
chmod 400 <filename>
```

#### Week 3: Corpus Processing

On week 3 we learned about different kinds of formatted text files such as .csv files as well as text processing. We learned about regular expressions, sed and tr.
I had used some regular expression before, but sed an tr were new to me. I also learned how to pipe commands, which is very useful.
For example, if I wanted to search all the words that end with -ing from a text file and find out which is more common I could use the commands I learned and find out 
with a code like this:  
```
cat <textfile> | grep -Eo "[A-Z]?[a-z]+ing\b" | sort | uniq -c | sort -nr | less
```    
Cat reads the file, grep searches the words that end in -ing, sort sorts them in 
alphabetical order, uniq combines the lines with the same word and  sort -nr puts them in reverse numerical order, thus showing first which is the most common word ending 
in -ing.

#### Week 4: Scripting and UNIX Configuration Files

On week 4 we looked at environment variables and scripts. I learned about configuration files such as the .bashrc file, which the shell reads everytime it opens so you 
can modify it to change how 
your shell works. For example, you can modify your prompt or create shortcuts for commands like this:
```
alias ls='ls -G'
alias h='history'
alias l='less'
```
Alias will create the shortcut so when you now just press 'l', your shell will know you mean 'less'.

We also learned how to make scripts and to run them, I learned that you must be really careful with nano and how one extra space can make it so that your script does not 
work even though otherwise it is correct. We learned that different types of scripts have different formats and how variables such as $ can be very useful when making 
scripts. Here is an image of a script I made:  

![Script](/assets/img/CMD.png)  
This script checks if two input files have differences or not and prints out only 0 if true and 1 if not.

#### Week 5: Installing and Running Programs

On week 5 we looked at installing software. We looked at pagckage managers, such as pip for python and how they make installing a lot easier. 
We learned about Makefiles, which is a file where you can put commands and then execute the Makefile with the command make. For example, in a Makefile you can include 
something like this:  
```
data/%.no_md.txt: data/%.txt
        python3 src/remove_gutenberg_metadata.py $< $@
```    
This is a make rule which removes the metadata from all of my .txt files from my data directory using python. 

#### Week 6: Version Control

On week 6 we looked at version control, which I learned is a way to manage changes to your projects. I learned to use Git and Github and how to work on changes on 
branches and only when I am content with the branch do I combine it with the master branch to commit the change to the main project. I learned that Git it useful because 
even if you make mistakes, Git is tracking your work all the time so you can always go back to any version of your work that worked best. To create a branch and merge it 
with your master branch you must do these steps:  
1. create a new branch with `git branch <branch name>`
2. switch to working on that branch with `checkout <branch name>`
3. after making the changes you want you need to add the file you were working on to the staging area with `git add -A` and then commit the changes with `git commit -m 
"description of change"`
4. you need to merge the branch with the master branch with `git push origin master`


#### Week 7: Building Webpages using Github Pages
