---
title: 'Rollback to previous commits'
date: 2018-05-27
permalink: /posts/2018/05/rollbackgit/
tags:
  - Git
---

**Taken from <https://gist.github.com/StefanoMagrassi/6c78b6f48599377a5c805fd58a5cd93d>**

Creat a branch using previous commit:

```
# Use two commands:
git checkout 0d1d7fc32
git checkout -b new_branch_name

# Use only one command
git checkout -b old-state 0d1d7fc32
```

**Always use `git branch` to check where you are before you make changes.** (If you've made changes, 
as always when switching branches, you'll have to deal with them as appropriate. You could reset to throw them away; 
you could stash, checkout, stash pop to take them with you; you could commit them to a branch there if you want a branch there.)


## Make current branch a master branch
```
git reset --hard better_branch
git push -f origin master
```

Note that this will delete your collaborator's changes. You can also use
```
git checkout better_branch
git merge --strategy=ours master    # keep the content of this branch, but record a merge
git checkout master
git merge better_branch             # fast-forward master up to the merge
```
#### Taken from <https://stackoverflow.com/questions/2763006/make-the-current-git-branch-a-master-branch>


## Hard delete unpublished commits

If you made a commits, but you have not push it to Github. You can go to previous commits using:
```
# This will destroy any local modifications.
# Don't do it if you have uncommitted work you want to keep.
git reset --hard 0d1d7fc32

# Alternatively, if there's work to keep:
git stash
git reset --hard 0d1d7fc32
git stash pop
# This saves the modifications, then reapplies that patch after resetting.
# You could get merge conflicts, if you've modified things which were
# changed since the commit you reset to.
```


## Undo published commits

On the other hand, if you've published the work, you probably don't want to reset the branch, since that's effectively 
**rewriting history**. In that case, you could indeed revert the commits. With Git, revert has a very specific meaning: create a 
commit with the reverse patch to cancel it out. This way you don't rewrite any history.


```
# This will create three separate revert commits:
git revert a867b4af 25eee4ca 0766c053

# It also takes ranges. This will revert the last two commits:
git revert HEAD~2..HEAD

# Reverting a merge commit
git revert -m 1 <merge_commit_sha>

# To get just one, you could use `rebase -i` to squash them afterwards
# Or, you could do it manually (be sure to do this at top level of the repo)
# get your index and work tree into the desired state, without changing HEAD:
git checkout 0d1d7fc32 .

# Then commit. Be sure and write a good message describing what you just did
git commit
```


#### taken from <http://stackoverflow.com/a/4114122>