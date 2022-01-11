# Linux shell commands

This markdown file aims to provide an overview of commonly-used Linux commands, as we will be using a series of bioinformatics tools throughout the course on Linux environment. This is not a comprehensive Linux tutorial but just some basic ones for students who may not familiar with using terminal.

## What is terminal?
 
The operating system (OS) on your computer consists of a `kernel`, and a `shell`. To instruct your computer, or `kernel` what to do, we can simply click and drag in most of the laptops nowadays. However, a computer doesn't have to have a graphical interface, imagining we are in a situation where we do not have any graphical interfaces, how can we switch between different directory/drives, create new file/folders, or even rename the files? Now we will need to type in our instructions through `terminal` which allows us to programmatically access `shell`, and in turns help us to reach the `kernel`.

## Navigating File System
```bash
# pwd
pwd
# cd
cd /
cd ~
cd .
cd ..
cd /Users/ligk2e/Desktop
# ls
ls
ls -l
ls -al
ls -alh
# clear
clear
```

## Read and Write the files
```bash
# read
cat file.txt
# write (end your inputs by Ctrl + D)
cat > file.txt
vim file.txt  # type i to enter "insert" mode, type escape to exit "insert" mode, to save your change, type ":w" and hit enter, to exit vim, type ":q" and hit enter.
nano file.txt  # much easier, just modify, then Ctrl + X to save, follow the prompts
```

## Common file/folder manipulation
```bash
# create a new folder
mkdir folder
# copy
cp file.txt ../
cp -R folder ../
# move
mv file.txt ../
mv folder ../
# rename
mv file.txt new_name_file.txt
# delete
rm file.txt
rm -r folder
```
