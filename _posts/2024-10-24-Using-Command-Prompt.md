---
title: Using Command Prompt with GitHub Repos
description: A little guide to using Command Prompt for GitHub repos
author: Jan
date: 2024-10-24
categories: [5. Guides, Command Line Interface]
tags: [command line interface, tutorial, command prompt]
---
# List of my most used command line commands

| Command                                           | Description                       |
| :------------------------------------------------ | :-------------------------------- |
| git init                                          | initialises git                   |
| git status                                        | status of current commit          |
| git add<file>                                     | include a file to the commit      |   
| git add .                                         | add all untracked files           |
| git commit -m "commit message here                | commits all the tracked files     |
| git log                                           | display commit log                |
|                                                   |                                   |
| git checkout <branch name>                        | switch branch                     |
| git branch                                        | show branches log                 |
| git branch <branch name>                          | create new branch                 |
| git merge <branch name>                           | merge branch into master          |
| git branch -d <branch name>                       | delete branch                     |
|                                                   |                                   |
| git remote add origin <url>                       | connect local dir to GitHub repo  |
| git push -u origin master                         | push master to repo               |
| git pull <url>                                    | pulls new commits and merges      |
|                                                   |                                   |
| git stash save <--keep-index --include-untracked> | save uncommited changes to stash  |
| git stash drop                                    | drop changes                      |

# Overview
Starting off with any Command Line Interface (CLI) can feel as daunting as ever. This guide is to help you get started using command prompt for your Github repos.

> If there is something that hasn't been covered in this blog, feel free to reach out on [LinkedIn](https://www.linkedin.com/in/janhuss/) and let me know, thanks =)
{: .prompt-info }

Once you have setup your repository on GitHub, create a folder in the location you would like your repo to be stored in.

Next, we need to load command prompt. There are several ways to do this. I'll go through the quickest way first:

## Changing the directory - The quickest way {#qw}

1. While in the folder, press `ctrl + l` to highlight the directory
2. Type `cmd` and hit `enter` on the keyboard

> !!! INSERT IMAGE HERE !!!
{: .prompt-warning }

![dir1](/assets/img/tutorials/cmdprmt/dir1.png){: width="600"}

The command prompt will launch and be set to the drive and directory of the folder you called it from

## Changing the directory - The longer way

Another way to open command prompt is by pressing the `Windows` icon and typing out `command prompt` or `cmd` and then select it.

> !!! INSERT IMAGE HERE !!!
{: .prompt-warning }

![dir2](/assets/img/tutorials/cmdprmt/dir2.png){: width="600" }

The issue with this is that you will automatically have your directory set to the default location, which you probably don't want.

> !!! INSERT IMAGE HERE !!!
{: .prompt-warning }

![wrongdir](/assets/img/tutorials/cmdprmt/wrongdir.png){: width="600" }

To change the directory:
1. Go to the folder location and copy its directory

> !!! INSERT IMAGE HERE !!!
{: .prompt-warning }

![copydir](/assets/img/tutorials/cmdprmt/copydir.png){: width="600" }

2. Then return to the command prompt and type:

```text
cd <paste directory in here>
```

3. Then hit enter

You should now see that the directory has changed.

## Changing the directory to a different drive
If you would like to change the directory to a different drive, for example from `C:` to `D:`, then you will need to add a few characters:

```text
cd /d <paste directory in here>
```

Hit enter

## Changing directory - to `C:` drive
To change back to the `C:` drive just type 

```text
C:
```

Hit enter

## Initialise git
In order for the directory to communicate with the GitHub repo, you will need to initialise it

```text
git init
```

## Clone repo
Now you can clone the repo! To do so, go to your repository and copy the link under the green `Code` button by pressing the copy button as shown in the image

> !!! INSERT IMAGE HERE !!!
{: .prompt-warning }

![cloneurl](/assets/img/tutorials/cmdprmt/cloneurl.png){: width="600"  }

Back on command line type the following

```text
git clone <paste URL here>
```

and hit enter.

Command prompt will start downloading the repository for you. Once finished downloading, check the directory if the contents of your repo are there.

Well done! You have cloned your repo! That wasn't that hard right? But what if you make changes to the repo? Well let's look at that next

## Pushing changes to the repository
Once you have made changes to the repo load command prompt if you have closed it and set the directory back to your repo location. Check the [Changing the directory - The quickest way] {#qw} section of this post.

Now type: 

```text
git add .
```

Make sure there is a space between `add` and `.`

Then type:

```text
git commit -m"add a commit message here."
```

People usually write what changes have been made since the last commit.
With that, your changes are ready to be pushed to the main branch, so let's do that:

```text
git push
```

And with that you will be able to see the changes made on your Github repository.

## Pulling git repo
Let's say you made changes to the repo on a different device and you want to pull the changed contents onto your home computer.

```text
git pull
```

That is all.

## Creating a branch
So far, we have been pushing and pulling from the `main` branch. That's not considered good practice.
In a real world scenario, each developer would work on a branch until the new feature is implemented.
**Only** then would they merge their changes to the `main` branch.

So let's create a new branch! I mean we're confident with command prompt by now, right?

```text
git checkout -b <name your branch>
```

To ensure that people know what you're working on, it's good practice to name your branch accordingly.

When you're ready to merge your branch to `main`:

```text
git merge <branch name here>
```

## Conclusion
So let's wrap up here. I hope that this little guide has given you a bit more confidence in using command prompt! There are so many other CLI out there such as GitBash and PowerShell. Not only do CLI give you ultimate flexibility in managing your repository, but you can also feel like a **Matrix god diving into the "Main Frame"** lol. 
