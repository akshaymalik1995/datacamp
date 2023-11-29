# Saving files

Now let's explore how Git stores information, along with looking at a workflow to update files and check their status.

## A repository
To start, let's discuss the components of a Git project. We'll be working with a project about mental health in tech throughout the course, which is shown here.

There are two parts - the first is the files and directories that we create and edit, in this case a funding document, a markdown file containing a report, and a directory called data.

The second part is the extra information that Git records about the project's history. The combination of these two things is called a repository, often referred to as a repo. Git stores all of its extra information in a directory called `.git`, located in the main directory of the repo. Git expects this information to be laid out in a particular way, so we should not edit or delete `.git`.

## Staging and committing
Now let's discuss how to make changes in a repo. We save a draft by placing it in a staging area. We save files, and update the repo in the process, through a commit.

Putting files in the staging area is like placing a letter in an envelope, while making a commit is like putting the envelope in a mailbox. We can add more things to the envelope or take things out as often as we want, but once we put it in the mailbox we can't make further changes.

## Accessing the .git directory

Although we shouldn't edit the `.git` directory, it may be helpful to see what's inside. It won't display when using the shell `ls` command, as it's a hidden directory. A hidden directory is a directory not displayed to users, typically because it stores information to enable programs to run. But if we add the `-a` flag it shows up along with some hidden files!

## Making changes to files
Let's visualize the Git storage workflow. Here, we modify a markdown file called `report.md`, and store five draft updates to the staging area as we progress. We commit, or save, the second and fifth versions of the file in the staging area, and with each commit our `.git` directory is modified to reflect the state of the repo.

## Git workflow
So, our Git workflow is to modify a file, save the draft to the staging area, commit the updated file to our repo, and repeat!

## Modifying a file
To execute this workflow we can use nano to open a text editor for the report file. We add three lines of text and save it using control-O and control-X.

## Saving a file
To add the updated file to the staging area we use the command `git add` followed by the filename. Alternatively, we can add all modified files in the current directory using `git add .`, as a dot represents all files and directories in our current location.

## Making a commit
We then commit our drafts using `git commit`. We add the `-m` flag to allow us to include a log message about our commit, placing it in quotes. The log message is important as we can refer to it later. Best practice is to keep it short and concise.

## Check the status of files
If we are making lots of changes then it's useful to know the status of our repo. We can use the `git status` command, which tells us which files are in the staging area, and which files have changes that aren't in the staging area yet. In this case, we see `report.md` has been modified and is in the staging area, so we make a commit.

