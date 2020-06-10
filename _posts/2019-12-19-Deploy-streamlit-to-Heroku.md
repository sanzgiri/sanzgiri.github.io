---
title: Deploy Streamlit to Heroku
date: 2019-12-20 00:00:00 Z
permalink: "/Deploy-streamlit-to-Heroku-2019-12-20"
layout: post
excerpt: Deploy-streamlit-to-Heroku, 2019-12-20
---
### Deploy streamlit app to Heroku (on mac)
```
# Install heroku
brew install heroku/brew/heroku

# Setup autocomplete for heroku
heroku autocomplete

# The app you are deploying has to be in a github repo (private is ok). An example repo is 
# https://github.com/MaartenGr/streamlit_guide.git
# The repo should contain a Procfile, a setup.sh file and requirements.txt containing any package dependencies
# The streamlit app should be named app.py and in the root directory. These are the must have files

# Steps to deploy your app
heroku login

# This sets up the heroku remote
heroku create

# Push code and trigger an action that launches your app
git push heroku master

# Scale app runtine for free usage
heroku ps:scale web=1

# Connect to your app on xxx.herokuapp.com
heroku open

# To rename app from xxx.herokuapp.com to newname.herokuapp.com, change app name in settings, then from local repo 
git remote rm heroku
heroku git:remote -a <newname>

# To setup custom domain e.g. easyai.ml
heroku domains add:www.easyai.ml.  # subdomain
heroku domains add:easyai.ml.      # root domain
heroku domains                     # list dns record types and targets

# Add CNAME entry for subdomain with name www, TTL 300 and target of form xxx.herokudns.com (no trailing dot)
# Add CNAME entry for root domain with name www, TTL 300 and target of form xxx.herokudns.com (no trailing dot)

# To confirm setup is complete. Changes will take some time to propagate
host www.easyai.ml
host easyai.ml

# Each of the commands above should say that <host> is an alias for <xxx.herokudns.com>
```
