The ULCDC project's awesome documentation site. To make modifications to the textual content, you should be able to easily edit files through GitHub's edit interface. 

Written using Jekyll (http://jekyllrb.com/)

I used rbenv to get the correct version of Ruby running on my mac.

Use Homebrew to install rbenv (note: incompatible with rvm): 

    brew update
    brew install rbenv ruby-build

Following the instructions from the rbenv install, I added to my .bash_profile:

    if which rbenv > /dev/null; then eval "$(rbenv init -)"; fi
    source ~/.bash_profile

Navigate to the folder I'm using to develop these pages in:

    cd ~/Projects/ucldc-docs

Set up a local ruby environment in this folder:

NOTE: as of Oct. 6, 2015 the github-pages gem requires ruby version 2.0 or
greater, the gem public_suffix require 2.0

    rbenv local 2.0.0-p647
    rbenv rehash

Then I followed the instructions [here](https://help.github.com/articles/using-jekyll-with-pages) (https://help.github.com/articles/using-jekyll-with-pages) to get jekyll up and running. This uses Bundler and the github-pages gem, to ensure your setup most closely resembles how GitHub Pages works to host your Jekyll site. 

    gem install bundler
    rbenv rehash

Bundler wasn't playing nice with rbenv for the bundle install command, so I ran:

    gem install github-pages

make a file named Gemfile and add 

    source 'https://rubygems.org'
    gem 'github-pages'

At this point, you can clone this repository: 

    git clone https://github.com/ucldc/ucldc-docs/

checkout the gh-pages branch: 

    git checkout -b gh-pages origin/gh-pages

comment out the url line of _config.yml by putting hash (#) in front of it: so  'url: "http://ucldc.github.io"' becomes '#url: "http://ucldc.github.io"'

Finally, run the Jekyll server:

    bundle exec jekyll serve

I usually add the --watch flag to jekyll serve. This flag watches for changes in the jekyll source files and automatically builds and serves changed files. 
