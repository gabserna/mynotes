W1D3

git push -u origin master
git status

origin = master repository

Files tracked by git
Comitted= unmodified changed from the last commit snapshot

Modified= changes made to files since last commit snapshot

Staged=changes marked to be added into the next commit snapshot
--------------

//to add files to commit write...
git add filename.txt

open -a atom filenametoedit.txt

git status -s OR --short

M= Modified
A= new file Added to staging area
??= new file untracked by git


Diff command
git diff --staged

Compared
diff --git a/file1.txt b/file1.txt

Change marker for fil A/B
---a/file1.txt
+++b/file1.txt

Chunk reader
@@ -12, 2 +12 3 @@

Chunk changes
- old content
+ new content

git diff --staged --no-renames
git commit -a -m "add new vendor"
git status

git log
git log -1
git log --oneline
git log --stat
git log --patch

open https://cbea.ms/git-commit/

The seven rules of a great Git commit message

1 Separate subject from body with a blank line
2 Limit the subject line to 50 characters
3 Capitalize the subject line
4 Do not end the subject line with a period
5 Use the imperative mood in the subject line
6 Wrap the body at 72 characters
7 Use the body to explain what and why vs. how

to remove a file we first need to ask git to stop tracking it
git rm filename
answer:
rm 'filename'

git status
-------------
git rm --cached filename
answer:
rm 'filename'
----------
git mv README.md README
git status
------------------------
branches
http://git-school.github.io/visualizing-git/

git checkout -b branch_name

git stash
git stash list
git stash show

merge
git merge branch_name
----------------
CAUTION
git reset --soft
git reset --mixed
git reset --hard

git clone (link to clone)
************************************************
git init
touch filename.ext
git add filename.ext
git status
echo "# repo_name" >> filename.ext
git add . (or instead of . filename.ext)(adds files to stage area)
git commit -a -m "changes I just made" (-a is for ALL files)
git remote add origin linktorepository
git push -u origin master (will promt username and passwd)
************************************************
git status (to see)
git log (to know if you are log in)

**edit txt files**
code filename.txt
notepad filename.txt
************************************************
--1st browse the right folder with files to submit--
git init
git add .
git commit -a -m "changes I just made"
git remote add origin linktorepository
git push -u origin master
************************************************
when stuck with "non-fast-forward" message
use:
git push -f -u origin <name of branch>
