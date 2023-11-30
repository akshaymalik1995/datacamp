# Comparing files

We've seen the workflow for drafting and saving updates, but if we are making lots of changes we need a way to compare versions as we make modifications!

## Why compare files?
Perhaps we've made changes to a machine learning model, but we're getting poorer performance as a result. We want to revert our changes, but can't remember what the code for the model looked like previously.

## Comparing a single file
Luckily, Git provides commands for checking the current state of our files versus at other times. Suppose we want to edit the `report.md` file. Inside the text editor, we add two lines representing tasks to complete.

## Updating the file
We've only edited one file, so we can use `git add .` to add the report to the staging area. We then commit our changes.

## Updating the file again
A while later we need to update the file again, this time removing the executive summary task and adding a reminder to cite the funding source. We can compare the last committed version of a file with the unstaged version by using the `git diff` command followed by the `filename`.

## Comparing an unstaged file with the last commit
The output shows two versions of `report.md`, where `a` is the first version, or the last one to be saved, and `b` is the second, or the one we have not added to the staging area.

The line with the two `@` symbols tells us the location of the changes, where the pairs of numbers represent the start line and number of lines. The minus one and five shows one line was removed at line five, and the plus one and five shows one line was added back in at line five.

Lines starting with a minus symbol written in red have been removed, the executive summary line in this case, and lines starting with a plus symbol and written in green have been added - which is the last one.

![image](https://github.com/akshaymalik1995/datacamp/assets/55041489/c626699c-db9c-4cf8-a947-89c8ca186d98)


## Comparing a staged file with the last commit
What if we had already added the file to the staging area? We can use the `git diff` command again, but this time we add the `-r` flag to indicate we want to look at a particular revision of the file. Adding `HEAD`, which is a shortcut for the most recent commit, allows us to see a difference between the report file in the staging area and the version in the last commit. Note that the `-r` flag won't work if we don't put `HEAD` afterwards.

```
git diff -r HEAD filename
```
As we can see, the output gives us the same information as using `git diff` for a file that hasn't been added to the staging area!

## Comparing multiple staged files with the last commit
What if we have more than one file in the staging area? Here we use `cd` to switch into the data directory, use nano to modify `mh-tech-survey.csv` to add an extra participant's survey responses, then add the file to the staging area.

In this case, we can use `git diff -r HEAD` to show the difference between all files in the staging area. In the output, we can see two files have been modified. One new line was added to the end of the `mh-tech-survey.csv` file, shown in green, along with the two changes to the report.

## Recap
To recap, if we want to compare an unstaged file with the last commit we use `git diff filename`. To see a staged file versus the last commit we run `git diff -r HEAD filename`. For comparing all staged files with the last commit it's `git diff -r HEAD`.
