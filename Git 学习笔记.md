- `HEAD`指向的版本就是当前版本，因此，Git允许我们在版本的历史之间穿梭，使用命令`git reset --hard commit_id`。
- 穿梭前，用`git log`可以查看提交历史，以便确定要回退到哪个版本。

要重返未来，用`git reflog`查看命令历史，以便确定要回到未来的哪个版本。

1. git init 初始化git 工程

2. git add . 添加修改到暂存区

3. git commit -m "modify reason" 提交到本地仓库

4. git log --pretty=oneline 查看提交日子

5. git reflog 查看所有日子 包括回退（reset）

6. git diff -- <file> 查看工作区文件修改（add 后的文件对比）， git diff head -- <file>查看和提交后文件的区别

7. git checkout -- <file> 回滚到暂存区的内容

8. git reset head <file> 把暂存区放到工作区， 要到达svn revert，需要先git reset head 然后再自行git checkout --

9. git reset --hard <commit id> 回退到某个提交的版本

10. git remote add origin git@github.com:<username>/learngit.git 把本地git项目同步到github上

11. git push -u origin master 第一次把本地的推动到github上

12. git push  origin master 推动本地提交代码到github

13. git clone 克隆远程库

14. git checkout -b dev 创建并切换到dev分支 （相当于git branch dev / git checkout dev）

15. git branch 查看所有分支

16. git merge dev 把分支上提交的合并到master上

17. git log --graph --pretty=oneline --abbrev-commit 查看带图形的并且commit id缩写

     

    $ git log --graph --pretty=oneline --abbrev-commit

    \*   20737bc (HEAD -> master) seventh version

    |\

    | * 1593098 ( feature1) fifth version

    \* | 1c37f4d sixth version

    |/

    \* 03386de (origin/master ) forth version from dev

    \* 3762229 thrid version

    \* acc048f second version

    \* e857aaa first version

18. git merge dev 把分支上提交的合并到master上

19. git stash 把当前修改隐藏起来，恢复到改之前的版本

20. git stash list 查看说有隐藏版本

21. git stash pop 恢复到隐藏版本，并删除stash

22. git branch -d <branch> 删除分支， -D强制删除分支

23. git push origin dev 在远端创建dev分支

24. git checkout -b dev origin/dev 从远端checkout dev分支

25. git branch --set-upstream-to=origin/dev dev 关联远端的dev和本地dev分支

26. git rebase 让提交到历史主线上 跟直观

27. git tag <tag name> 新建标签，默认是最新的commit上

28. git tag -a <tag name> -m "comment" 

29. git tag 查看所有标签

30. git tag -d <tag name> 删除标签

31. git push origin <tag name> 或者 git push origin --tags 推送到远端

32. git push origin :refs/tags/<tag name> 再删除本地tag后，执行命令删除远端的

presented by

TOWER

›

Version control with Git - made easy

Version control with Git - made easy

30-day free trial available at

www.git-tower.com

GIT

CHEAT SHEET

fournova

CREATE

Clone an existing repository

$ git clone ssh://user@domain.com/repo.git

Create a new local repository

$ git init

LOCAL CHANGES

Changed files in your working directory

$ git status

Changes to tracked files

$ git diff

Add all current changes to the next commit

$ git add .

Add some changes in <file> to the next commit

$ git add -p <file>

Commit all local changes in tracked files

$ git commit -a

Commit previously staged changes

$ git commit

Change the last commit

Don‘t amend published commits!

$ git commit --amend

COMMIT HISTORY

Show all commits, starting with newest

$ git log

Show changes over time for a specific file

$ git log -p <file>

Who changed what and when in <file>

$ git blame <file>

BRANCHES & TAGS

List all existing branches

$ git branch -av

Switch HEAD branch

$ git checkout <branch>

Create a new branch based

on your current HEAD

$ git branch <new-branch>

Create a new tracking branch based on

a remote branch

$ git checkout --track <remote/bran

\-

ch>

Delete a local branch

$ git branch -d <branch>

Mark the current commit with a tag

$ git tag <tag-name>

UPDATE & PUBLISH

List all currently configured remotes

$ git remote -v

Show information about a remote

$ git remote show <remote>

Add new remote repository, named <remote>

$ git remote add <shortname> <url>

Download all changes from <remote>,

but don‘t integrate into HEAD

$ git fetch <remote>

Download changes and directly

merge/integrate

into HEAD

$ git pull <remote> <branch>

Publish local changes on a remote

$ git push <remote> <branch>

Delete a branch on the remote

$ git branch -dr <remote/branch>

Publish your tag

s

$ git push --tags

MERGE & REBASE

Merge <branch> into your current HEAD

$ git merge <branch>

Rebase your current HEAD onto <branch>

Don‘t rebase published commits!

$ git rebase <branch>

Abort a rebase

$ git rebase --abort

Continue a rebase after resolving conflicts

$ git rebase --continue

Use your configured merge tool to

solve conflicts

$ git mergetool

Use your editor to manually solve conflicts

and

(after resolving) mark file as resolved

$ git add <resolved-file>

$ git rm <resolved-file>

UNDO

Discard all local changes in your working

directory

$ git reset --hard HEAD

Discard local changes in a specific file

$ git checkout HEAD <file>

Revert a commit

(by producing a new commit

with contrary changes)

$ git revert <commit>

Reset your HEAD pointer to a previous commit

...and discard all changes since then

$ git reset --hard <commit>

...and preserve all changes as unstaged

changes

$ git reset <commit>

...and preserve uncommitted local changes

$ git reset --keep <commit>

presented by

TOWER

›

Version control with Git - made easy

Version control with Git - made easy

30-day free trial available at

www.git-tower.com

GIT

CHEAT SHEET

fournova

CREATE

Clone an existing repository

$ git clone ssh://user@domain.com/repo.git

Create a new local repository

$ git init

LOCAL CHANGES

Changed files in your working directory

$ git status

Changes to tracked files

$ git diff

Add all current changes to the next commit

$ git add .

Add some changes in <file> to the next commit

$ git add -p <file>

Commit all local changes in tracked files

$ git commit -a

Commit previously staged changes

$ git commit

Change the last commit

Don‘t amend published commits!

$ git commit --amend

COMMIT HISTORY

Show all commits, starting with newest

$ git log

Show changes over time for a specific file

$ git log -p <file>

Who changed what and when in <file>

$ git blame <file>

BRANCHES & TAGS

List all existing branches

$ git branch -av

Switch HEAD branch

$ git checkout <branch>

Create a new branch based

on your current HEAD

$ git branch <new-branch>

Create a new tracking branch based on

a remote branch

$ git checkout --track <remote/bran

\-

ch>

Delete a local branch

$ git branch -d <branch>

Mark the current commit with a tag

$ git tag <tag-name>

UPDATE & PUBLISH

List all currently configured remotes

$ git remote -v

Show information about a remote

$ git remote show <remote>

Add new remote repository, named <remote>

$ git remote add <shortname> <url>

Download all changes from <remote>,

but don‘t integrate into HEAD

$ git fetch <remote>

Download changes and directly

merge/integrate

into HEAD

$ git pull <remote> <branch>

Publish local changes on a remote

$ git push <remote> <branch>

Delete a branch on the remote

$ git branch -dr <remote/branch>

Publish your tag

s

$ git push --tags

MERGE & REBASE

Merge <branch> into your current HEAD

$ git merge <branch>

Rebase your current HEAD onto <branch>

Don‘t rebase published commits!

$ git rebase <branch>

Abort a rebase

$ git rebase --abort

Continue a rebase after resolving conflicts

$ git rebase --continue

Use your configured merge tool to

solve conflicts

$ git mergetool

Use your editor to manually solve conflicts

and

(after resolving) mark file as resolved

$ git add <resolved-file>

$ git rm <resolved-file>

UNDO

Discard all local changes in your working

directory

$ git reset --hard HEAD

Discard local changes in a specific file

$ git checkout HEAD <file>

Revert a commit

(by producing a new commit

with contrary changes)

$ git revert <commit>

Reset your HEAD pointer to a previous commit

...and discard all changes since then

$ git reset --hard <commit>

...and preserve all changes as unstaged

changes

$ git reset <commit>

...and preserve uncommitted local changes

$ git reset --keep <commit>

CREATE

Clone an existing repository

$ git clone ssh://user@domain.com/repo.git

Create a new local repository

$ git init

LOCAL CHANGES

Changed files in your working directory

$ git status

Changes to tracked files

$ git diff

Add all current changes to the next commit

$ git add .

Add some changes in <file> to the next commit

$ git add -p <file>

Commit all local changes in tracked files

$ git commit -a

Commit previously staged changes

$ git commit

Change the last commit

Don‘t amend published commits!

$ git commit --amend

COMMIT HISTORY

Show all commits, starting with newest

$ git log

Show changes over time for a specific file

$ git log -p <file>

Who changed what and when in <file>

$ git blame <file>

BRANCHES & TAGS

List all existing branches

$ git branch -av

Switch HEAD branch

$ git checkout <branch>

Create a new branch based

on your current HEAD

$ git branch <new-branch>

Create a new tracking branch based on

a remote branch

$ git checkout --track <remote/bran

\-

ch>

Delete a local branch

$ git branch -d <branch>

Mark the current commit with a tag

$ git tag <tag-name>

UPDATE & PUBLISH

List all currently configured remotes

$ git remote -v

Show information about a remote

$ git remote show <remote>

Add new remote repository, named <remote>

$ git remote add <shortname> <url>

Download all changes from <remote>,

but don‘t integrate into HEAD

$ git fetch <remote>

Download changes and directly

merge/integrate

into HEAD

$ git pull <remote> <branch>

Publish local changes on a remote

$ git push <remote> <branch>

Delete a branch on the remote

$ git branch -dr <remote/branch>

Publish your tag

s

$ git push --tags

MERGE & REBASE

Merge <branch> into your current HEAD

$ git merge <branch>

Rebase your current HEAD onto <branch>

Don‘t rebase published commits!

$ git rebase <branch>

Abort a rebase

$ git rebase --abort

Continue a rebase after resolving conflicts

$ git rebase --continue

Use your configured merge tool to

solve conflicts

$ git mergetool

Use your editor to manually solve conflicts

and

(after resolving) mark file as resolved

$ git add <resolved-file>

$ git rm <resolved-file>

UNDO

Discard all local changes in your working

directory

$ git reset --hard HEAD

Discard local changes in a specific file

$ git checkout HEAD <file>

Revert a commit

(by producing a new commit

with contrary changes)

$ git revert <commit>

Reset your HEAD pointer to a previous commit

...and discard all changes since then

$ git reset --hard <commit>

...and preserve all changes as unstaged

changes

$ git reset <commit>

...and preserve uncommitted local changes

$ git reset --keep <commit>



GIT 配置：