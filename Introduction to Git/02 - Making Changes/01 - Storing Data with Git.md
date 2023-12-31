# Storing data with Git
Time to explore the commit structure in detail. We'll examine how Git stores data and the process for viewing this information.

## The commit structure
Git stores data through commits, which have three parts. The first is the commit itself, which contains metadata such as the author, commit message, and time of the commit. The second part is a tree, which tracks the names and locations in the repo when that commit happened. For each file listed in the tree, there is a blob, which is short for binary large object. A blob may contain data of any kind. Blobs contain a compressed snapshot of the contents of the file when the commit happened.

## Visualizing the commit structure


![image](https://github.com/akshaymalik1995/datacamp/assets/55041489/849ace98-900a-48d5-a19e-6d126427eaa2)


Here, we visualize three commits to our repo to see these three individual components.

In the first commit, we can see a unique identifier ending in six-five. This identifier is known as a hash, which we will discuss later. In the tree, we see two files were modified - `report.md` and `mental-health-survey.csv`. The blob shows a snapshot of what the files contained at that time.

In the second commit, there are three files in the tree, but only two were modified - `mental-health-survey.csv` and a newly created `summary-statistics.csv`. Therefore, the tree links `report-dot-md` to the blob from the previous commit, as it wasn't modified in this commit.

In the third and most recent commit, `report-dot-md` and `mental-health-survey-dot-csv` are modified, with updated blobs created and linked to the tree. The summary statistics file wasn't changed, so the tree links to the blob in the second commit.

## Git log

We can view commit information using the `git log` command, which will display all commits made to the repo in chronological order, starting with the oldest. It will show the commit hash, author, date, and commit message. If the output doesn't fit in the terminal window, there will be a colon at the end of the output, indicating there are more commits. We can move through the history by pressing the space bar. When we want to exit the log we can press `q` to return to the terminal.

## Git hash
Earlier, we mentioned a unique identifier called a hash. This is a 40 character string of numbers and letters. It is called a hash because Git produces it using a pseudo-random number generator called a hash function. Hashes enable Git to share data efficiently between repos. If two files are the same, their hashes will be the same. Therefore, Git can tell what information needs to be saved in which location by comparing hashes rather than entire files.

## Finding a particular commit
Suppose we have observed issues since a particular date. We need to see what changed in a commit on that day to cause the issues. First we'll need to identify which commit caused the issue, so we run `git log` to view all commits and note the hashes for commits on the day in question. We only need to note the first six-to-eight characters of the hash. We can then run `git show` followed by the start of the hash for each commit in turn, until we find the commit we are looking for.

## Git show output
The output of `git show` displays the log entry for that commit at the top, followed by a `diff` output showing changes between the file in that commit and the current version in the repo. At the bottom we see the added line appears to have data in the wrong order, with gender in the first column instead of the second. This looks like the source of the issue!

