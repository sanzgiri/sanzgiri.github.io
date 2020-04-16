---
toc: true
layout: post
description: Creating auto-updating notebooks and blog posts with FastPages
categories: [jupyter]
title: Creating auto-updating notebooks and blog posts with FastPages
---

# Creating auto-updating notebooks and blog posts with FastPages

* Assumes you have a blog set up using FastPages. If not, you can quickly create one going through the steps listed [here](https://github.com/fastai/fastpages). Note that you can create multiple FastPages blogs inside your github account, each in a separate repo.

* Add an `update-nb.yaml` file to directory `<repo>.github/workflows` in your blog repo. Starting points for this file are: [update-nb.yaml template](https://github.com/github/covid19-dashboard/blob/master/.github/workflows/update-nb.yaml) (or a trimmed version here that does not use issues to trigger or monitor your workflow: [my trimmed template](https://github.com/sanzgiri/covid-19-dashboards/blob/master/.github/workflows/update-nb.yaml)

    - The only things to change here are the cron schedule (question - can you set up a separate schedule by notebook?)

    - Update the `install dependencies` section with any steps you need for your notebooks to run

* Add run_notebooks.sh to directory `<repo>/_action_files`. The template I started with was: 
[run_notebooks.sh template](https://github.com/github/covid19-dashboard/blob/master/_action_files/run_notebooks.sh)

    - In this file you can control which notebooks get updated on the schedule you have set up.

* Add the notebooks to directory `<repo>/_notebooks`. Specific rules for how to customize your notebook so that it looks "good" when coverted to a blog post can be seen here: [Notebook commands for FastPages](https://github.com/fastai/fastpages#writing-blog-posts-with-jupyter)

* That is basically it! Once these code changes are checked in, Github Actions will get scheduled per your cron settings in `update-nb.yaml`. You can monitor the actions from the Actions link in the toolbar at the top of the github link for your repo. You can view the steps inside the `Update Notebooks And Refresh Page` action. If there are any errors, the messages are pretty explanatory.

## References
* [Github Actions](https://fastpages.fast.ai/actions/markdown/2020/03/06/fastpages-actions.html)