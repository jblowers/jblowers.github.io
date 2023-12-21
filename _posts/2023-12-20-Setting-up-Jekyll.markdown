---
title: "Setting up Jekyll for blog posting functionality"
layout: post
---

## 12/20/2023

Steps to set up my Jekyll install! lol

Had to take a bunch of hacks to get it to run from WSL on Windows (might have been something I did wrong — never installed or used Ruby/gem or any of the bundler stuff).

### These are my steps:

#### A bunch of install steps:

```
sudo apt-get update
sudo apt-get install ruby-full build-essential zlib1g-dev
sudo apt-get install rbenv ruby-build
# These might not have been necessary
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(rbenv init -)"' >> ~/.bashrc
source ~/.bashrc
# End of potentially unnecessary
gem install bundler
```


I actually had to use sudo with all the gem and bundle calls -- it warned me this was a bad idea, but I couldn't get it to go without it.  
Likely a consequence of this, I also had to manually install (with sudo) a number of dependencies in order for 
`bundle install`
to run correctly.  

* Once that was all set up though, I could create the blog files within my repo by using
```jekyll new rusty-quest-blog```
* moved into that directory and ```bundle install```
* Then to add a page!  
I fought with it a bit, but then realized I need to name the file correctly under _posts
Needs to match this format: `2023-12-20-test-page-1.markdown`


## A couple other things I had to do today 
I needed to set up ssh for git (rather than mess with passwords and such)  

* for this, I followed these steps
* `eval "$(ssh-agent -s)"`
* `ssh-add ~/.ssh/id_rsa`
* Add the public key to my github account
* Then I had to change the remote url for my already existing git repo:
* `git remote set-url origin git@github.com:jblowers/rusty_quest.git`
