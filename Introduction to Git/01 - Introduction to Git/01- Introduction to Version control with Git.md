# Introduction to version control with Git

Hi! My name is George, and in this course we'll learn how to use Git for version control.

## What is a version?
Before we discuss Git and version control, let's define a version, which is the **contents of a file at a given point in time**. It also includes metadata, or information associated with the file, such as the author, where it is located, the file type, and when it was last saved.

## What is version control?
Version control is a group of systems and processes to manage changes made to documents, programs, and directories. Version control isn't just for software. Anything that changes over time or needs to be shared can benefit from using version control.

Version control allows us to track files in different states and let multiple people work on the same files simultaneously, a concept known as continuous development. It also allows us to combine different versions, identify a particular version of a file, and revert changes.

## Why is version control important?

To illustrate why version control is essential when working with data, consider a common scenario of modifying a dataset. We save separate copies at various time intervals, using fairly similar names. We then produce new analyses as the dataset changes, but matching these outputs to the correct data can be difficult as time goes by!

Put another way, a data project without version control is like cooking without a recipe - it'll be difficult to remember how to produce the same results again.

## Git
One popular program for version control is called Git. Git is open source and scalable to easily track everything from small solo projects to complex collaborative efforts with large teams! Note that Git is not the same as GitHub, which is a cloud-based Git repository hosting platform. However, it's common to use Git with GitHub!

## Benefits of Git
A key benefit of Git is that it stores everything, so nothing is ever lost. Also, Git automatically notifies us when our work conflicts with someone else's, so it's harder to accidentally overwrite content. Additionally, Git can synchronize work done by different people on different machines.

## Using Git
A common method to use Git is via the shell, also known as the terminal. The shell is a program for executing commands. Before we use Git, we'll run through some shell commands that will often be used in our version control workflow, such as previewing, modifying, and inspecting files or directories. Note that a directory is often referred to on a computer as a folder.

## Useful shell commands
To see our location, we can execute `pwd`, which stands for print working directory. Here, we are in the `Documents` directory of a user called `Repl` i.e. `/home/repl/Documentts`. To see what is in our current directory we can use the `ls` command. This returns a list of all files and directories. There is a directory called `archive` and three csv files.

## Changing directory
If we need to change directory, we can execute `cd` followed by the directory we want to move into. Here, we navigate to the `archive` directory. Rechecking our location confirms we have successfully moved.

## Editing a file
We can even use the shell to preview and modify files. In the documents directory, we use the `nano` command followed by the filename, which opens a text editor. We can delete, add, or change contents of a file, and save using `control + o`, then exit the editor using `control + x` to return to the shell.

We can also use `echo` to create or edit a file. Here, we create a file called `todo.txt`.
```
echo "Review for duplicated records" > todo.txt
```
If the file already exists, then we can append content by using two arrows instead of one.
```
echo "Review for duplicated records" >> todo.txt
```

## Checking Git version
Different versions of software have different functionality, and Git is no exception. We can check which version of Git we have installed by typing `git --version` in the shell.

