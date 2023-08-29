# README.md

## Installation and usege

Jekyll's [documentation](https://jekyllrb.com) is awesome. I almost didn't even write this. However, I did want to add a few things that I found useful. Primarily, deploying to GitHub pages.

```sh
gem install bundler jekyll
jekyll new my-awesome-site
cd my-awesome-site
bundle exec jekyll serve
# => Now browse to http://localhost:4000 
```

## Deploying to GitHub Pages

The best way to deploy to GitHub pages is to use a branch called gh-pages. This branch will be used to host the site. The master branch will be used to host the source code. This is a common pattern for GitHub pages.

There is a gem to do this for jekyll 3.0 but I was unable to get it to work on 4.x so we will have to do it by hand.

Because this is a common pattern outside of jekyll I will reference the git documentation instead. Migrating a [folder to a branch](../git/folder-as-branch.md) in git.
