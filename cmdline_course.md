---
layout: default
---

### COMMAND-LINE COURSE

This course was an introduction to command-line tools for linguists. We learned about command-line environments such as terminal and basic commands to use the 
environments and process texts. We looked at UNIX file systems and software packages as well as version control and Github. The most challenging part of the course for me 
was making scripts. I think I had to use a lot of the things we had learned to get the scripts to work, which was useful and I feel like I learned a lot when I tried to 
get them to work.
I liked this course and I think I learned a lot about the basics of command-line.

#### Week 1: Introduction to Command-Line Environments

First week we looked at terminal and basic commands as well as different types of files.
I had used terminal before, so I was familiar with the basic commands such as wget, echo and mv. However, there were some new commands as well, for example that you can 
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

On week 2 we learned about the UNIX file system, permissions and processes. All of this was new to me. I learned about the root user, which is a user in UNIX that can 
do basically anything and you might need to switch to root user to execute some commands. You can also change the permissions of some files with chmod. For example, if 
you want to give only read rights to only the owner of a file you could use the command 
```
chmod 400 <filename>
```

#### Week 3: Corpus Processing

On week 3 we learned about different kinds of formatted text files such as .csv files as well as text processing. We learned about regular expressions and the commands 
sed and tr.
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
This script checks if two input files have differences or not and prints out 0 if true and 1 if not.

#### Week 5: Installing and Running Programs

On week 5 we looked at installing software. We looked at package managers, such as pip for python and how they make installing a lot easier. 
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
even if you make mistakes, Git is tracking your work all the time so you can always go back to any version of your work that worked best. To create a local branch and 
merge it with your remote master branch you must do these steps:  
1. create a new branch with `git branch <branch name>`
2. switch to working on that branch with `checkout <branch name>`
3. after making the changes you want you need to add the file you were working on to the staging area with `git add -A` and then commit the changes with `git commit -m 
"description of change"`
4. you need to push the branch with the changes to your remote repository with `git push origin <branch name>`
5. to merge that with the master branch you need to change to the local master branch with `checkout master`
6. merge `git merge <branch name>`
7. push the new master branch to the remote repository with `git push origin master`


#### Week 7: Building Webpages using Github Pages

On week 7 we learned about Jekyll and more about Github pages. Jekyll is a static site generator and it is useful for things such as our final assingment of the course, 
which is to build a website with Github. With Jekyll you can easily check the changes you make without having to push them to the remote Github repository. It will create 
a static site that you can view on your own computer. To get Jekyll to generate the site, you need to use the command  
```
bundle exec jekyll serve
```  
 
We also learned about markdown and the specific ways to format text with markdown.
