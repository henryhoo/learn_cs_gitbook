# Git Minimal Guide

### Why writing this tutorial

It took me more than one year to fully master git. Before that, I can't agree more on one of the quote in [this YCombinator post](https://news.ycombinator.com/item?id=4200492):

> Can we please stop pretending that Git is simple and easy to learn? If that were true then there wouldn't be "Learn how to use Git in  minutes!" posts every other day.

Truth is, **the core idea behind Git is not complicated. However it can still be hard to get started and mastered**. :\)

Most of current tutorial assume you already have some background in computer science \(that make sense, since Git is majorlly used for managing codes\). However, those assumptions make a tutorial harder for true beginners. Another thing that hard for begineers is Git has so many new terms like _repository_ and _commit_, which are hard to concretize without using Git for a while.

So I become yet another person trying to write yet another tutorial for Git & GitHub.

This tutorial aims to only require **minimal experience in command line**, and will try to **associate Git specific concepts with some everyday procedure** to help everyone to understand Git without cursing someone.

Side note: If you want to learn about command line, the best way is to google it: [example search](https://www.google.com/search?ei=8SBxX8PGAou8sAX084uoDw&q=learning+command+line&oq=learning+command+line&gs_lcp=CgZwc3ktYWIQAzIECAAQQzICCAAyAggAMgIIADICCAAyBggAEBYQHjIGCAAQFhAeMgYIABAWEB4yBggAEBYQHjIGCAAQFhAeOgQIABBHUPEOWPEOYI8QaABwA3gAgAFyiAFykgEDMC4xmAEAoAEBqgEHZ3dzLXdpesgBCMABAQ&sclient=psy-ab&ved=0ahUKEwiDg5inv4rsAhULHqwKHfT5AvUQ4dUDCA0&uact=5).

### How to use this tutorial

Git is really a _tool_, it is not a _technology_ that you need to learn for a full semester of college class like [compiler](https://en.wikipedia.org/wiki/Compiler). However, **to fully master a tool, you need to use it everyday**. It is all about an old saying --- _Practice makes perfect_.

So the best way to learn with this tutorial is **running all the steps in each section by yourself, and then try to recap what happened based on explanation in that section.**

To help you with this process. Each section is break down into three parts:

* **Explanation** that explain what we will do and what it means in Git
* **Execution** that document what you need to run on your own computer
* **Expected Result** that help you confirming you are running everything correctly

### Let's start

#### Section 1: Getting start with command line and install Git

**Explanation**

We will learn to run some basic commands in terminal and install Git. Then we will make sure Git is installed correctly by checking the version of current installed Git on you laptop.

**Execution**

* You will need to know how to use command line, the best way is to [find some existing tutorials in Google](https://www.google.com/search?ei=8SBxX8PGAou8sAX084uoDw&q=learning+command+line&oq=learning+command+line&gs_lcp=CgZwc3ktYWIQAzIECAAQQzICCAAyAggAMgIIADICCAAyBggAEBYQHjIGCAAQFhAeMgYIABAWEB4yBggAEBYQHjIGCAAQFhAeOgQIABBHUPEOWPEOYI8QaABwA3gAgAFyiAFykgEDMC4xmAEAoAEBqgEHZ3dzLXdpesgBCMABAQ&sclient=psy-ab&ved=0ahUKEwiDg5inv4rsAhULHqwKHfT5AvUQ4dUDCA0&uact=5).
* Follow [this guide](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) to install git on your laptop.
* Open terminal and run your first command

  ```bash
  git --version
  ```

**Expected Result**

You should see your current installed git version \(it might different from mine `2.24.3` which is totally fine\)

```bash
% git --version
git version 2.24.3 (Apple Git-128)
```

#### Section 2: Set up Git

**Explanation**

* We will go to your Desktop in termianl using `cd` command
* We will create a new folder named _learnGit_ in your desktop using `mkdir` command.
* We will initialize git for in _learnGit_ folder using `git init` command.
* We will add git user information \(name & email\) using `git config` command. It will help Git to know who is making changes in the future \(like add a signature for your documents\).

**Execution**

* Run following commands in terminal \(Just run them, don't need to know what it means, I will explain later\):

  ```bash
  cd ~/Desktop
  mkdir learnGit
  cd learnGit
  git init
  git config user.name "Bob"
  git config user.email "Your name here"
  git config user.email "Bob@xxx.com"
  ```

**Expected Result**

```bash
% cd ~/Desktop
% mkdir learnGit
% cd learnGit
% git init
Initialized empty Git repository in /Users/jxh/Documents/jiaxi/learnGit/.git/
% git config user.name "Bob"
% git config user.email "Bob@xxx.com"
```

#### Section 3: First commit

**Explanation**

We will create a new file _learnGit_ folder and add it as first commit in Git

* `echo` append some text contents to a file
* `git status` command to check current status of the folder, we will see our new file under untracked files
* `git add` command to start tracking the new file, this means any change to this file will be recorded in Git
* `git commit` command to make our first commit, which includes our changes to the new file.
* `git log` and `git status` command again to make sure new commit is saved and no new change is presented currently

**Execution**

* Run following commands in terminal \(Just run them, don't need to know what it means, I will explain later\):

  ```bash
  echo "this is V0 content" >> file.txt
  git status
  git add file.txt
  git status
  git commit -m "add file.txt to V0"
  git log
  git status
  ```

**Expected Result**

```bash
$ echo "this is V0 content" >> file.txt
$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
    file.txt

nothing added to commit but untracked files present (use "git add" to track)
$ git add file.txt
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
    new file:   file.txt

$ git commit -m "add file.txt to V0"
[master (root-commit) 8bb5621] add file.txt to V0
 1 file changed, 1 insertion(+)
 create mode 100644 file.txt
$
$ git log
commit 8bb5621de624af17c0524bd3c1e2e02cee499e4e (HEAD -> master)
Author: Bob <Bob@xxx.com>
Date:   Sun Nov 1 21:54:20 2020 -0500

    add file.txt to V0
$ git status
On branch master
nothing to commit, working tree clean
```

#### Section 4: Second commit

**Explanation**

We will make some changes \(append a new line\) to file.txt and add the changes as second commit

* `git diff` to see what is changed in the file
* Then wrun same step as \#3 to save the change as a new commit

**Execution**

* Run following commands in terminal \(Just run them, don't need to know what it means, I will explain later\):

  ```bash
  echo "this is V1 content" >> file.txt
  git diff
  git status
  git add file.txt
  git status
  git commit -m "update file.txt"
  git log
  git status
  ```

**Expected Result**

```bash
$ echo "this is V1 content" >> file.txt
$ git diff
diff --git a/file.txt b/file.txt
index 7ee650f..55b579d 100644
--- a/file.txt
+++ b/file.txt
@@ -1 +1,2 @@
 this is V0 content
+this is V1 content
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
    modified:   file.txt

no changes added to commit (use "git add" and/or "git commit -a")
$ git add file.txt
$ git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
    modified:   file.txt

$ git commit -m "update file.txt"
[master 43e6c4c] update file.txt
 1 file changed, 1 insertion(+)
$ git log
commit 43e6c4cbb0191669a066393de601c996d4970dce (HEAD -> master)
Author: Bob <Bob@xxx.com>
Date:   Sun Nov 1 22:02:51 2020 -0500

    update file.txt

commit 8bb5621de624af17c0524bd3c1e2e02cee499e4e
Author: Bob <Bob@xxx.com>
Date:   Sun Nov 1 21:54:20 2020 -0500

    add file.txt to V0
$ git status
On branch master
nothing to commit, working tree clean
```

#### Section 5: Go back to V0

**Explanation**

We no longer need V1 and want to back V0 version, so we will run

* `git checkout 8bb5621de624af17c0524bd3c1e2e02cee499e4e` to go back to first commit
* `git log` and `cat` command to check file content and make sure the file is from V0 version

**Execution**

* Run following commands in terminal \(Just run them, don't need to know what it means, I will explain later\):

  ```bash
  git checkout 8bb5621de624af17c0524bd3c1e2e02cee499e4e
  git log
  cat file.txt
  ```

**Expected Result**

```bash
$ git checkout 8bb5621de624af17c0524bd3c1e2e02cee499e4e
Note: switching to '8bb5621de624af17c0524bd3c1e2e02cee499e4e'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 8bb5621 add file.txt to V0
$ git log
commit 8bb5621de624af17c0524bd3c1e2e02cee499e4e (HEAD)
Author: Bob <Bob@xxx.com>
Date:   Sun Nov 1 21:54:20 2020 -0500

    add file.txt to V0
$ cat file.txt
this is V0 content
```

#### Section 6: Go back to V1

**Explanation**

After second thought, we actually need V1 and want to find it back, so we will run

* `git checkout master` to go back to second commit
* `git log` and `cat` command to check file content and make sure the file is from V1 version

**Execution**

* Run following commands in terminal \(Just run them, don't need to know what it means, I will explain later\):

  ```bash
  git checkout master
  git log
  cat file.txt
  ```

**Expected Result**

```bash
$ git checkout master
Previous HEAD position was 8bb5621 add file.txt to V0
Switched to branch 'master'
$ git log
commit 43e6c4cbb0191669a066393de601c996d4970dce (HEAD -> master)
Author: Bob <Bob@xxx.com>
Date:   Sun Nov 1 22:02:51 2020 -0500

    update file.txt

commit 8bb5621de624af17c0524bd3c1e2e02cee499e4e
Author: Bob <Bob@xxx.com>
Date:   Sun Nov 1 21:54:20 2020 -0500

    add file.txt to V0
$ cat file.txt
this is V0 content
this is V1 content
```

### Recap

Wow~~~ We finished our first tutorial! In this section we learn to set up Git enviornoment on our laptop, created our first local repository, recorded file changes as commits and learnt to switch between different commits.

The Git command we have used so far

* `git status`
* `git diff`
* `git log`
* `git add`
* `git commit`
* `git status`
* `git checkout`

In next section we will learn to how to upload our local changes to remote repository GitHub and work with others.

