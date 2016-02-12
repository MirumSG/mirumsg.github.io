---
layout: post
title:  "Git Team Workflow"
date:   2015-04-17
categories: best practices html
---

##Master branch
---
The `master` branch is always deployable. There shouldn't be any half written code or bug in it.
`master` branch always shows the current state of a production/release code (the same set of code int live server).
Any new team member should always pull code from `master` branch.

##Develop branch
---
The `develop` branch is the main branch for ongoing development. Feature branches are created from and merged back into the `develop` branch.
When implementing a new feature, branch from `develop` and start doing the changes.

##Feature branch
---
If a branch is a fix to some bug, prepend the branch name to `fix-` E.g: `fix-add-boomark-count`.
And if the branch is add new features, prepend the branch name to `feature-` E.g: `feature-video-playlist`.

**Always remember, `master` and `develop` branch should never be worked in directly, always branch out to work.**


##Rebase /merge
---
When a feature or a fix is completed, make sure that your feature branch has the latest changes from the `develop` branch because there may be conflicts.
All conflict resolution should be fix in your feature branch. If you branched to make a small change/fix and you have not pushed the branch to the remote, rebase `develop` into your feature branch, and then merge your feature branch into `develop`. Push and then feel free to delete your local feature branch.

If you have pushed your branch to the remote, first merge `develop` into your branch (resolving conflicts), and then merge your branch into `develop`. Push and feel free to delete both the local and remote feature branch.

Remember, rebasing is a **destructive** action. Here are a couple of rules to keep you safe when rebasing:

* Never rebase anything that has been pushed to the remote. Is the branch you're on only local? Then it is good to rebase. Otherwise, no rebasing.
* Rebase shared branches in local branches. develop is a shared branch. `my‑awesome-feature` is a local branch. Now I'm ready to merge `my‑awesome‑feature` into develop, but I want to make sure any changes that have happened in `develop` are merged into my feature branch first:

```
git checkout my-awesome-feature
git rebase develop
git checkout develop
git merge my-awesome-feature
```


As long as the updated code is still on staging, keep it in the `develop` branch. Only merge the code back into `master` when the updated changes are push to live.

***\*Always remember to merge `develop` into `master` after live!.***

##Adhoc hotfix
---
If there is some major bug found on live site and we need to address it immediately, since `develop` may include unfinished features, hotfixes should be branched from the current release—which is `master` (because `master` is always deployable!).

To make a hotfix, branch off `master`, make the fix and then merge into `master`. Tag it, then merge master back into `develop` (because we'll want `develop` to have the fix too). After merging, delete the hotfix branch.

