# Github workflow  

A brief introduction of github flow presented by Yijun Li, 516030910395.

![img](http://m.c.exp1.licdn.com/mpr/mpr/AAEAAQAAAAAAAATiAAAAJGI1ZTdmYmJiLWUzMzktNGE3NC05OGM4LTI5NTA2MWRkYWY3Yw.png)

## What?

> GitHub Flow is a lightweight, branch-based workflow that supports teams and projects where deployments are made regularly.            ----Github Guides

## Why?

* Every one in the team has his own local repo. Avoid interrupting others' work.

* Push once after committing multiple times.

* Pull request enables code review.

* After evaluating the output, only have to merge once and then consider new demands.

  #####_Comparison between SVN and GIT:_

  **1-workflow:**

  **-GIT:**

  - A Git repository stores the full history of all of its branches and tags within the *.git*
  - The latest stable release is contained within the master
  - Active feature work is developed in separate branches.
  - When a feature is finished, the feature branch is merged into masterand deleted.

  **-SVN:**

  - The trunk directory represents the latest stable release of a project.
  - Active feature work is developed within subdirectories under branches.
  - When a feature is finished, the feature directory is merged into trunk and removed.

  **2- Distribution:**

  **-Git **is Distributed Revision Control System which means, every developers checking out code from central repository/server will have their own cloned repository installed on their machine.

  **-SVN **have centralized Revision Control System, or server

  **3-Storing data:**

  **-Git** stores content as metadata

  **-SVN** stores content as  files

  **4-Revision:**

  **-GIT** does not have a global revision no

  **-SVN’**s revision no. is a snapshot of source code at any given time

  **5-Location and size:**

  Imagine you are a developer on the road, you develop on your laptop and you want to have source control so that you can go back 3 hours*.*

  **With Git**, you do not have the SVN problem. Your local copy is a repository, and you can commit to it and get all benefits of source control. When you regain connectivity to the main repository, you can commit against it.

  **With Subversion**, you have a Problem: The SVN Repository may be in a location you can't reach (in your company, and you don't have internet at the moment), you cannot commit. If you want to make a copy of your code, you have to literally copy/paste it.

  **6-content integrity:**

  **GIT **contents are cryptographically hashed using [SHA-1](http://en.wikipedia.org/wiki/SHA-1) hash algorithm.This will ensure the robustness of code contents by making it less prone to repository corruption due to disk failures, network issues etc

  **SVN** doesnt have a hashed contents.This will risk to lose code and contents due to disk failure , network issues

## How?

### 1.Create a branch

When you're working on a project, you're going to have a bunch of different features or ideas in progress at any given time – some of which are ready to go, and others which are not. Branching exists to help you manage this workflow.

When you create a branch in your project, you're creating an environment where you can try out new ideas. Changes you make on a branch don't affect the `master` branch, so you're free to experiment and commit changes, safe in the knowledge that your branch won't be merged until it's ready to be reviewed by someone you're collaborating with

![屏幕快照 2017-10-28 下午4.37.20](/Users/darlenelee/Desktop/屏幕快照 2017-10-28 下午4.37.20.png)

####*Protip*

Branching is a core concept in Git, and the entire GitHub Flow is based upon it. There's only one rule: anything in the `master` branch is always deployable.

Because of this, it's extremely important that your new branch is created off of master when working on a feature or a fix. Your branch name should be descriptive (e.g., `refactor-authentication`, `user-content-cache-key`, `make-retina-avatars`), so that others can see what is being worked on.

### 2.Add commits

Once your branch has been created, it's time to start making changes. Whenever you add, edit, or delete a file, you're making a commit, and adding them to your branch. This process of adding commits keeps track of your progress as you work on a feature branch.

Commits also create a transparent history of your work that others can follow to understand what you've done and why. Each commit has an associated commit message, which is a description explaining why a particular change was made. Furthermore, each commit is considered a separate unit of change. This lets you roll back changes if a bug is found, or if you decide to head in a different direction.

![屏幕快照 2017-10-28 下午4.37.31](/Users/darlenelee/Desktop/屏幕快照 2017-10-28 下午4.37.31.png)

#### *ProTip*

Commit messages are important, especially since Git tracks your changes and then displays them as commits once they're pushed to the server. By writing clear commit messages, you can make it easier for other people to follow along and provide feedback.

### 3.Open a Pull Request

Pull Requests initiate discussion about your commits. Because they're tightly integrated with the underlying Git repository, anyone can see exactly what changes would be merged if they accept your request.

You can open a Pull Request at any point during the development process: when you have little or no code but want to share some screenshots or general ideas, when you're stuck and need help or advice, or when you're ready for someone to review your work. By using GitHub's @mention system in your Pull Request message, you can ask for feedback from specific people or teams, whether they're down the hall or ten time zones away.

![屏幕快照 2017-10-28 下午4.37.37](/Users/darlenelee/Desktop/屏幕快照 2017-10-28 下午4.37.37.png)

#### *ProTip*

Pull Requests are useful for contributing to open source projects and for managing changes to shared repositories. If you're using a Fork & Pull Model, Pull Requests provide a way to notify project maintainers about the changes you'd like them to consider. If you're using a Shared Repository Model, Pull Requests help start code review and conversation about proposed changes before they're merged into the master branch.

### 4.Discuss and review your code

Once a Pull Request has been opened, the person or team reviewing your changes may have questions or comments. Perhaps the coding style doesn't match project guidelines, the change is missing unit tests, or maybe everything looks great and props are in order. Pull Requests are designed to encourage and capture this type of conversation.

You can also continue to push to your branch in light of discussion and feedback about your commits. If someone comments that you forgot to do something or if there is a bug in the code, you can fix it in your branch and push up the change. GitHub will show your new commits and any additional feedback you may receive in the unified Pull Request view.

![屏幕快照 2017-10-28 下午4.37.44](/Users/darlenelee/Desktop/屏幕快照 2017-10-28 下午4.37.44.png)

#### *ProTip*

Pull Request comments are written in Markdown, so you can embed images and emoji, use pre-formatted text blocks, and other lightweight formatting.

### 5.Deploy

Once your pull request has been reviewed and the branch passes your tests, you can deploy your changes to verify them in production. If your branch causes issues, you can roll it back by deploying the existing master into production.

![屏幕快照 2017-10-28 下午4.37.51](/Users/darlenelee/Desktop/屏幕快照 2017-10-28 下午4.37.51.png)

### 6.Merge

Now that your changes have been verified in production, it is time to merge your code into the master branch.

Once merged, Pull Requests preserve a record of the historical changes to your code. Because they're searchable, they let anyone go back in time to understand why and how a decision was made.

![屏幕快照 2017-10-28 下午4.37.57](/Users/darlenelee/Desktop/屏幕快照 2017-10-28 下午4.37.57.png)

#### *ProTip*

By incorporating certain keywords into the text of your Pull Request, you can associate issues with code. When your Pull Request is merged, the related issues are also closed. For example, entering the phrase `Closes #32` would close issue number 32 in the repository.

## Drawbacks

* For enterprises:

  1. high price
  2. difficulty to learn for all team members

* For individuals:  

  1. too slow to load the website; 

  2. not friendly to Chinese characters;

  3. weak Wiki functions

     ​