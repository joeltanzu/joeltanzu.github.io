---
layout: post
title: Squashing Commits for a Clean Repository
categories: git
---

One of the initial problems faced while setting up this website was the multitude of commits that I needed to make. Imagine having a list of 30+ commits before even getting the website up and running! While having multiple commits is nothing wrong, it would be cleaner if you could have the option of squashing multiple commits relating to the same issue. Github pages, by virtue of utilising Git, gives you that powerful option of manipulating your commit history to achieve that goal. 

First, if you have not done so yet, it is much advisable to download the [GitHub Desktop application](https://desktop.github.com/). It offers a clean GUI for users not seasoned with utilising the Git Command Line Inferface (CLI). After doing so, you will need to download [Git](https://git-scm.com/) as well in order to get the Git Bash CLI to do the commit squashing. You will be primarily using the GitHub Desktop application to handle the task, whereas Git serves the backend role. 

With both applications downloaded and installed, the next step is to open up GitHub Desktop and clone your GitHub pages repository into your system. This gives you the preferred option of editing your website through your local directory and thereafter committing the changes via the GitHub desktop application. With that done, you can finally do some squashing!

On the top left of the GitHub Desktop interface, make sure your current repository is set as your GitHub pages repository. Below the current repository selection box, selecting history will let you view all the past commits that you have done. This is important for you to view which commits you wish to squash.

Thereafter, head to the top bar and select 'Repository' followed by 'Open in Git Bash' (or use the keyboard shortcut Ctrl+'). This opens up the Git Bash CLI to do the commit squashing.

Squashing Commits:
* To squash N commits, type into Git Bash: git rebase -i HEAD~N (with N being the amount of past commits you wish to squash)
* Thereafter two notepad windows will open in succession. Save those notebooks and close after amending based on the details below.
* When the first notepad window opens: All commits listed will be set as 'pick'. Set those commits you wish to be squashed to 'squash' or 's'. Only one should be left as 'pick'
* When the second notepad window opens: Set your commit message. Recommendation is to delete everything auto generated for you and to write your own commit message that makes sense
* Check your history page, your commits should be squashed! But these are only local changes, now to get them into the server
* Note that you cannot push these changes using the normal method, and you will instead need to 'force' the changes
* Type into Git Bash: git push --force-with-lease 
* Check your GitHub account. Changes should be reflected on the website!