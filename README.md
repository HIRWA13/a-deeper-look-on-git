# A deeper look at git:

git is more than `git add`, `git commit`, and `git push`. It is a powerful tool that can be used to manage your code and collaborate with others. This repo will go over some of the more advanced features of git.

## 1. Editing a commit message:

Sometimes you make a commit and realize that you made a typo in the commit message. You can edit the commit message with the following command:

```bash

git commit --amend -m "New commit message"

```
### examples of commit editing steps:

```bash 

User@DESKTOP-72SEU4G MINGW64 ~/OneDrive/Desktop/Playground/Git/a-deeper-look-on-git (main)
$ git add test1.md && git commit -m 'Create first file'
[main (root-commit) 28f21c2] Create first file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md

User@DESKTOP-72SEU4G MINGW64 ~/OneDrive/Desktop/Playground/Git/a-deeper-look-on-git (main)
$ git add test2.md && git commit -m "Create send file"
[main f664013] Create send file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md

User@DESKTOP-72SEU4G MINGW64 ~/OneDrive/Desktop/Playground/Git/a-deeper-look-on-git (main)
$ git add test3.md && git commit -m "create third file and create a fourth file"
[main 157c923] create third file and create a fourth file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

User@DESKTOP-72SEU4G MINGW64 ~/OneDrive/Desktop/Playground/Git/a-deeper-look-on-git (main)
$ git status
On branch main
Your branch is based on 'origin/main', but the upstream is gone.   
  (use "git branch --unset-upstream" to fixup)

edit f664013 Create second file
Untracked files:
  (use "git add <file>..." to include in what will be committed)   
        test4.md

nothing added to commit but untracked files present (use "git add" to track)

User@DESKTOP-72SEU4G MINGW64 ~/OneDrive/Desktop/Playground/Git/a-deeper-look-on-git (main)
$ git add test4.md
Create second file

User@DESKTOP-72SEU4G MINGW64 ~/OneDrive/Desktop/Playground/Git/a-deeper-look-on-git (main)
$ git commit --amend
[main d2bde4b] create third file and create a fourth file
 Date: Wed Sep 20 07:25:39 2023 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md

User@DESKTOP-72SEU4G MINGW64 ~/OneDrive/Desktop/Playground/Git/a-deeper-look-on-git (main)
$ git log --oneline
d2bde4b (HEAD -> main) create third file and create a fourth file  
f664013 Create send file
28f21c2 Create first file

User@DESKTOP-72SEU4G MINGW64 ~/OneDrive/Desktop/Playground/Git/a-deeper-look-on-git (main)
$ git rebase -i HEAD~2
Stopped at f664013...  Create second file
You can amend the commit now, with

  git commit --amend

Once you are satisfied with your changes, run

  git rebase --continue

User@DESKTOP-72SEU4G MINGW64 ~/OneDrive/Desktop/Playground/Git/a-deeper-look-on-git (main|REBASE 1/2)
$ git commit --amend
[detached HEAD a2183ad] Create second file
 Date: Wed Sep 20 07:24:53 2023 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md

User@DESKTOP-72SEU4G MINGW64 ~/OneDrive/Desktop/Playground/Git/a-deeper-look-on-git (main|REBASE 1/2)
$ git rebase --continue
Successfully rebased and updated refs/heads/main.

User@DESKTOP-72SEU4G MINGW64 ~/OneDrive/Desktop/Playground/Git/a-deeper-look-on-git (main)
$ git log --one-line
fatal: unrecognized argument: --one-line

User@DESKTOP-72SEU4G MINGW64 ~/OneDrive/Desktop/Playground/Git/a-deeper-look-on-git (main)
$ git log
commit 88ec4764f25f35e99372b2eca31fee3feb657c70 (HEAD -> main)
Author: Junior Hirwa <iamhirwejr@gmail.com>
Date:   Wed Sep 20 07:25:39 2023 +0200

    create third file and create a fourth file

commit a2183adeb0bb81cc12136b1746f462f9e3b3e7e4
Author: Junior Hirwa <iamhirwejr@gmail.com>
Date:   Wed Sep 20 07:24:53 2023 +0200

    Create second file

commit 28f21c29409aa8dcdc08fc1d0fde75d068dc5bbf
Author: Junior Hirwa <iamhirwejr@gmail.com>
Date:   Wed Sep 20 07:24:23 2023 +0200

    Create first file

User@DESKTOP-72SEU4G MINGW64 ~/OneDrive/Desktop/Playground/Git/a-deeper-look-on-git (main)
$ git log --oneline
88ec476 (HEAD -> main) create third file and create a fourth file
a2183ad Create second file
28f21c2 Create first file

User@DESKTOP-72SEU4G MINGW64 ~/OneDrive/Desktop/Playground/Git/a-deeper-look-on-git (main)
$

```