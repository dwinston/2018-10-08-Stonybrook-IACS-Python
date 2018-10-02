# Git

diff, status, add, commit

commit, tree, blob (_b_inary _l_arge _ob_ject)

## .git directory
Suppose your home directory /home/repl contains a repository called dental,
which has a sub-directory called data. Where is information about the history of
the files in /home/repl/dental/data stored?

- home/repl/.git
- /home/repl/dental/.git (*)
- /home/repl/dental/data/.git
- None of the above

## git log

When you run git log, Git automatically uses a pager to show one screen of
output at a time. Press the space bar to go down a page or the 'q' key to quit.

You are in the directory dental, which is a Git repository. Use a single Git
command to view the repository's history. What is the message on the very first
entry in the log (which is displayed last)?

## git log path

You have been put in the dental repository. Use git log to display only the
changes made to data/southern.csv. How many have there been?

## hashes

Use cd to go into the dental directory and then run git log. What are the first
four characters of the hash of the most recent commit?

- bedc
- 2e1b
- 2e95
- None of the above (*)

## git show

You have been put in the dental directory. Use git log to see the hashes of
recent commits, and then git show with the first few digits of a hash to look at
the most recent commit. How many files did it change?

Reminder: press the space bar to page down through git log's output and q to
quit the paged display.

- None
- 1 (*)
- 2
- 4

## relative paths in git

You are in the dental repository. Using a single Git command, show the commit
made just before the most recent one. Which of the following files did it
change?

git show HEAD~1

- report.txt
- data/western.txt
- both of the above
- neither of the above

## git annotate

lets you see who modified a file and when.

## what changed between two commits?

You are in the dental repository. Use git diff to view the differences between
its current state and its state two commits previously. Which of the following
files have changed?

git diff HEAD..HEAD~2

## gitignore

Which of the following files would *not* be ignored by a .gitignore that
contained the lines:

```
pdf
*.pyc
backup
```

- report.pdf
- bin/analyze.pyc
- backup/northern.csv
- None of the above.

## git clean -f

Use `git status` to see status. Use `git clean -f` to remove unwanted files. Use
this command carefully.

## git config

git config --list [--system | --global | --local]

You are in the dental repository. How many local configuration values are set in
for this repository?

Set user.name and user.email for all projects for your user on your computer.

## undoing unstaged changes

Uses "--" to checkout from the staging area rather than from a commit identified
by a hash.

```
git checkout -- <file> ...
```

## undo changes to staged files

```
git reset HEAD path/to/file
git checkout -- path/to/file
```

## How do I restore an old version of a file?

`git log -3 <file>` to show last 3 commits. `git checkout <hash> <file>` to
checkout committed version. `cat` to display contents. `git commit` to commit
restored version.

## git branch

checkout another branch, `git rm` (`rm` + `git add`) a file, `git commit` that
change, `ls` to see that file isn't there, then `git checkout master` to see
that file is restored.

```
git checkout -b deleting-report
git rm report.txt
git commit -m "Removing report"
git diff master..deleting-report
```

## git init

New repo in new dir: `git init <name>`. Turn existing dir into repo: `git init
/path/to/dir` or `git init` inside dir. Then `git status`.

## git clone

`git clone /existing/project [newprojectname]`. Existing project on local
filesystem or remote server.

You have just inherited the dental data analysis project from a colleague, who
tells you that all of their work is in a repository in /home/thunk/repo. Use a
single command to clone this repository to create a new repository called dental
inside your home directory (so that the new repository is in /home/repl/dental).

## git remote

How can I find out where a cloned repository originated?

```
`git remote
git remote -v
git remote add <remote-name> <URL>
git remote rm <remote-name>
```

You are in the dental repository. Add /home/thunk/repo as a remote called thunk
to it.

## git pull

`git pull remote branch` gets everything in `branch` in the remote repository
identified by `remote` and merges it into the current branch of your local
repository.

You are in the master branch of the repository dental. Pull the changes from the
master branch of the remote repository called origin.

## git push

try push and fail, pull w/ merge commit, try push again.

# Nano

Ctrl-K: delete a line.
Ctrl-U: un-delete a line.
Ctrl-O: save the file ('O' stands for 'output').
Ctrl-X: exit the editor.

Run nano names.txt to edit a new file in your home directory and enter the
following four lines:
```
Lovelace
Hopper
Lim
Winston
```

To save what you have written, type Ctrl-O to write the file out, then Enter to
confirm the filename, then Ctrl-X and Enter to exit the editor.

# Bike Counting

- Step through first_run nb.
- Restart and run all
- create github repo w/ Python gitignore and MIT License
- git clone. move in nb. Start it.
- restart and run all
- add Fremont.csv to via `nano .gitignore`
- start package in jupyterdata. touch `__init__.py`.
- write `x = 5.9` in `__init__.py` and import from REPL.
- refactor fn to data.py. import and show `?`, shift-tab, `??` in nb.
- Write out test 'Scratch.ipynb'. Save to `jupyterworkflow/tests/test_data.py`.
- Use `python -m pytest jupyterworkflow` to test (`conda install pytest`)