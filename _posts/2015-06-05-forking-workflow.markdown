---
layout: post
title:  "Git Forking Workflow"
date:   2015-06-06
categories: best practices html git
---

|Steps                  |                                                    |
|-----------------------|----------------------------------------------------|
|Fork a copy from the main repo| ![](/images/forking-workflow/1-forking.png)|
|Generate SSH key| ![](/images/forking-workflow/2-gen-ssh.png) |
|Add generated SSH key into Github account| ![](/images/forking-workflow/3-add-ssh.png) |
|Clone your forked copy to your local computer| ![](/images/forking-workflow/4-clone.png)|
|Add upstream(main repo) in source tree| ![](/images/forking-workflow/5-upstream.png)|
|Pulling updates from upstream `master` branch| ![](/images/forking-workflow/6-pulling-upstream.png)|
|Create your `feature` branch| ![](/images/forking-workflow/7-create-branch.png)|
|Commit your changes into your forked repo| ![](/images/forking-workflow/8-commit-branch.png)|
|Merging your changes back into your forked `master` branch| ![](/images/forking-workflow/9-merging-master.png)
|Always pull updates from upstream `master` branch before starting a new feature to keep the code in sync| ![](/images/forking-workflow/11-checking-upstream.png)|
