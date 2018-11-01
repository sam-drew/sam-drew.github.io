---
layout: post
title: "Setting up GitHub Pages and Jekyll"
---

Combining GitHub Pages and the popular static site generator Jekyll can create a powerful tool for blogging and documentation hosting. This guide will focus on creating a site for a GitHub user or organisation, rather than per project (however they are not vastly dissimilar).  

You can find more information about GitHub/Jekyll integration [here](https://help.GitHub.com/articles/about-GitHub-pages-and-jekyll/).  

# Installing Jekyll

Jekyll isn't officially supported on Windows, however it can be used with some tweaks. More information on this is available in the [Jekyll docs](https://jekyllrb.com/docs/installation/windows).  

### Install Ruby and Bundler
1. Ensure that you have Ruby 2.1.0 or higher installed by opening a terminal and running the command:  
```
$ ruby --version
``` 

2. If Ruby is not installed, download and install it from the [Ruby website](https://www.ruby-lang.org/en/documentation/installation/).  

3. Once Ruby is installed, install Bundler by running the command:  
```
$ gem install bundler
```

### Install Jekyll
1. Create a new directory that will contain your site. This directory will become your Git repository, and as such *must* follow the GitHub pages repository naming convention:  
```
$ mkdir USER-OR-ORG-NAME.github.io
```

2. Ruby uses a file named Gemfile to track dependencies and build the Jekyll site. Navigate into the site directory, create a new file named ```Gemfile```, and add the following lines:  
```
source 'https://rubygems.org'
gem 'GitHub-pages', group: :jekyll_plugins
```  

3. Install Jekyll and dependencies:  
```
$ bundle install
```  

# Creating and deploying a site

### Create your Jekyll site
1. In your site directory, create a Jekyll template site:  
```
$ bundle exec jekyll _3.3.0_ new /
```

2. Using a text editor, open the ```Gemfile``` and remove the following line:  
```
"jekyll", "3.3.0"
```

3. Again using a text editor, uncomment (delete the ```#``` at the start of) this line:  
```
gem "GitHub-pages", group: :jekyll_plugins
```  

4. When developing a site locally, Jekyll can run a server that watches for changes to files and automatically updates the site as you work:  
```
$ jekyll serve
```

5. With this server running, navigate to ```http://localhost:4000``` in a web browser to preview the site.  

6. If you just want the site to build ready for pushing to deployment, use the command:  
```
$ jekyll build
``` 
 
Both ```serve``` and ```build``` create the HTML files needed to deploy the site in the ```_site``` directory. Usually ```serve``` will be used in development and ```build``` before deployment.  

### Deploy Jekyll site to GitHub Pages
1. Create a new **empty** remote repository on GitHub ensuring that it is named the same as the directory containing your Jekyll site. E.g.: ```USER-OR-ORG-NAME.github.io```

2. Navigate to the root directory of the site on your computer and initialise a Git repository:  
```
$ git init
```  

3. Connect the local repository containing your site with the remote repository on GitHub:  
```
$ git remote add origin https://github.com/USER-OR-ORG-NAME/USER-OR-ORG-NAME.gitub.io
```  

4. Make sure your site is built before commiting changes.  

5. Stage and commit your changes:  
```
$ git add .
$ git commit -m "COMMIT-MESSAGE"
```

6. Push you changes to the remote repository to publish your GitHub Pages site:  
```
$ git push -u origin master
```
The changes will take a few minutes to propagate, but after that your site will be available internet wide at ```USER-OR-ORG-NAME.github.io```. You can also configure GitHub Pages to use a custom domain name, more information on how to do this is available at [GitHub Help](https://help.github.com/articles/using-a-custom-domain-with-github-pages/).  

# Creating a new post

To create a new post, create a new file in the ```_posts``` directory of your site repository. Post file names are formatted like this:
```
YYYY-MM-DD-POST-TITLE.markup
```  
Where ```markup``` is the file extension of your chosen markup language. For example, the file name of this post (written in the markup language markdown) is:  
```
2018-10-31-github-pages-jekyll.md
```  
All post files begin with a front matter block which defines the title of the post, and other metadata. Front matter must be valid [YAML](http://yaml.org/) and be enclosed by triple dash lines. For example, the front matter for this post is:  
```
---
layout: post
title: "Setting up GitHub Pages and Jekyll"
---
```  
You can use front matter to set many [predefined variables](https://jekyllrb.com/docs/variables/), or you can create your own. Front matter is also used to categorise posts, using the ```category``` or ```categories``` variables.  

After you have a post file with a valid name and valid front matter, you can use your favourite markup language to write whatever you want, and Jekyll will build it into a nice looking static website. As previously mentioned, Jekyll can serve your site locally as you write - allowing you to check your changes look right as you make them:  
```
$ jekyll serve
```
When you're ready to publish your new post, build the site, commit, and push to GitHub:  
```
$ jekyll build
$ git commit -m "Added new post: POSTNAME"
$ git push -u origin master
```  
After a few moments, the new post will be available on your site.  

For more information about Jekyll visit their [website](https://jekyllrb.com).  
For more information about GitHub Pages, visit [GitHub Help](https://help.github.com/categories/github-pages-basics/).  

*Sam Drew, 31-10-18.*