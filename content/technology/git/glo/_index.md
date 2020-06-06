+++
title = "Glo Boards"
date = 2020-06-06T19:11:56+02:00
+++


The [GitKraken](https://www.gitkraken.com/) client also has a feature called Glo Boards. It is similar to Trello however it has better features that make it more desirable for developers. Here is an [article](https://blog.axosoft.com/gitkraken-glo-boards-vs-trello/) explaining the advantages of Glo Boards over Trello. Here are a few.

- First of all, it visually looks much cooler.
- Built in integration with Github issues.
- Much better search functionality

## Usage

You can add a synced board to one of your Github repos. Which means that all cards created on that board will become issues in your Github repo. This basically connects and syncs the two entities so you can track and organize your issues. 

## Workflow

1. Create cards in board to refer to issues and development.
2. Create commit that fixes issue related to card and use specific keywords in commit message to refer to fixing issues, explained [here](https://help.github.com/articles/closing-issues-using-keywords/). So use keywords like `Fix #12`, `Close #10`, or `Resolve #11` to close issues. Note, make sure the issue number e.g. `#10` has one of the keyword in front of it. Don't do this: `Fix #10, #12` , because only `#10` will be registered.
3. When the development branch is merged to the master branch, that is when the issues will be resolved on Github.