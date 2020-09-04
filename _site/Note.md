### Install missing gem executables with `bundle install`
### Don't use sudo to install bundle
### However sudo password is still needed during installation
bundle install

### Make sure that `gem install ??? -v '?.?.?'` succeeds before bundling.
sudo gem install eventmachine -v '1.2.7'
sudo gem install pathutil -v '0.16.2'
sudo gem install jekyll -v '4.1.1'

## Gem::InstallError:
## jekyll requires RubyGems version >= 2.7.0.
## Try 'gem update --system' to update RubyGems itself.
gem env version
sudo gem update --system

### Make sure to upgrade ruby to version 2.4 at least which can support 'bundle install'
sudo apt-get install ruby-dev
sudo apt update
sudo apt-get install ruby2.3 ruby2.3-dev

### Or try ruby 2.4 or 2.5
### You can get those via the brightbox PPA
## Add the repository and update
sudo apt-add-repository ppa:brightbox/ruby-ng && sudo apt-get update
### The computer needs to restart to finish installing updates.
## install for 16.04
sudo apt-get install ruby2.4 ruby2.4-dev
## or for 18.04
sudo apt-get install ruby2.5 ruby2.5-dev

###########################################################
## After successfully installed bundle: Bundle complete! ##
###########################################################
bundle exec jekyll serve


### If changes didn't appears, re-run the build.
### Or running 'jekyll serve' on Jekyll 2.4 should do this automatically.



## Web links:
## [1] https://github.com/jekyll/jekyll/issues/920
## [2] https://jekyllrb.com/docs/structure/
## [3] https://mmistakes.github.io/jekyll-theme-skinny-bones/getting-started/#adding-new-content
## [4] https://jekyllrb.com/docs/posts/


my=jekyll-site
.
|-- _pages
    |-- about.md
    |-- articles.md
|-- _config.yml
|-- _includes/
|-- _layouts/
|-- _posts/
|-- _site/
|-- index.md

