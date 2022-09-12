# Git Cheatsheet

[![N|Solid](https://icon-library.com/images/git-icon/git-icon-18.jpg)](www.linkedin.com/in/muhaimenul/)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://miobyte.com/muhaimenul)


### Basic initial git flow:

1. create repository
2. git clone clone-link
3. copy project to the clonned repository
4. git add . or git add -A
5. git commit -m "Give a token to remember"
6. git remote add origin clone-link
7. git push -u origin master
8. username password


### Edit git config:

```sh
git config --edit --global                        # edit global config
git config core.fileMode false                    # ignore file permission
```

### See Git Info:

```sh
git remote get-url origin
git config user.name
git config user.email
```


### See or change origin:

```sh
git remote -v
git remote add origin <url>
git remote add origin <url>
```

### Stage or Commit Related:

```sh
git show --summary                                # see last Commit
git reset --soft HEAD~1                           # undo last commit
git reset --hard 0ad5a7a6 or git checkout <sha1>  # return to specific commit
git stash                                         # hide you changes without commit
git stash list                                    # see your list with hidden changes
git stash apply                                   # apply your last changes from stash list
git stash drop stash@{0}                          # remove from stash list
git stash pop stash@{1}                           # apply choosed stash and drop it from stash list
```

### See history:

```sh
git log
git log --since='2 weeks ago'                     # for specific time
git whatchanged                                   # log with list of files
```

```sh
git blame filename.ext                            # see file modifier
git blame filename.ext -L 1,5                     # see file modifier within lines
```

### Pull-Push or Merge Related:

```sh
git pull --allow-unrelated-histories
```

```sh
git reflog                                        # undo a git pull
git reset --hard <VERSION_ID>                     # undo to a specific commit
git reset --hard master@{"30 minutes ago"}        # undo to a specific time
```

```sh
git status                                        # track changes
git diff --stat                                   # see the number of lines changed
```

### All about branch:

```sh
git branch                                        # branch list
git branch <name>                                 # create branch 
git checkout <name>                               # switch branch
git checkout -b <name>                            # create and switch branch
git merge <branch>                                # merge branch from master
git branch -d <branch>                            # delete local branch (-D for force delete)
git push origin --delete <branch>                 # delete remote branch
git merge local_branch                            # merge current branch with local_branch
git pull . local_branch                           # merge current branch with local_branch
```

### Replace user info of git commit:

```sh
git filter-branch -f --env-filter "
    GIT_AUTHOR_NAME='Muhaimenul Islam'
    GIT_AUTHOR_EMAIL='muhaimenulislam@iut-dhaka.edu'
    GIT_COMMITTER_NAME='Muhaimenul Islam'
    GIT_COMMITTER_EMAIL='muhaimenulislam@iut-dhaka.edu'
  " HEAD
```


#### References:
- https://docs.github.com/en/get-started/using-git/about-git
- https://docs.gitlab.com/ee/gitlab-basics/start-using-git.html