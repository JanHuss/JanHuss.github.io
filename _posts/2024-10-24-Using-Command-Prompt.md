---
title: Using Command Prompt with GitHub Repos
description: A little guide to using Command Prompt for GitHub repos
author: Jan
date: 2024-10-24
categories: [5. Guides, Command Line Interface]
tags: [command line interface, tutorial, command prompt]
---
# Overview
Starting off with any Command Line Interface (CLI) can feel as daunting as ever. This guide is to help you get started using command prompt for your Github repos.

> If there is something that hasn't been covered in this blog, feel free to reach out on [LinkedIn](https://www.linkedin.com/in/janhuss/) and let me know, thanks =)
{: .prompt-info }

Once you have setup your repository on GitHub, create a folder in the location you would like your repo to be stored in.

Next, we need to load command prompt. There are several ways to do this. I'll go through the quickest way first:

## Changing the directory - The quickest way

1. While in the folder, press `ctrl + l` to highlight the directory
2. Type `cmd` and hit `enter` on the keyboard

> !!! INSERT IMAGE HERE !!!
{: .prompt-warning }

The command prompt will launch and be set to the drive and directory of the folder you called it from

## Changing the directory - The longer way

Another way to open command prompt is by pressing the `Windows` icon and typing out `command prompt` or `cmd` and then select it.

> !!! INSERT IMAGE HERE !!!
{: .prompt-warning }

The issue with this is that you will automatically have your directory set to the default location, which you probably don't want.

> !!! INSERT IMAGE HERE !!!
{: .prompt-warning }

To change the directory:
1. Go to the folder location and copy its directory

> !!! INSERT IMAGE HERE !!!
{: .prompt-warning }

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

## Changing directory back to `C:` drive
To change back to the `C:` drive just type 

```text
C:
```

Hit enter
