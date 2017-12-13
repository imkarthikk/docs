---
date: 2013-07-24 00:00:00 +0000
description: How to deploy your static site using Forestry & GitHub Pages
related:
- title: GitHub "Hello World" Guide
  url: https://guides.github.com/activities/hello-world/
- title: GitHub Pages Whitelist
  url: https://pages.github.com/versions/
tags: ''
title: Deploying with GitHub Pages

---
With Forestry, you can deploy your static site using a branch on a GitHub repository. This requires you set up your site using a Git repository.

If you don’t have a GitHub account with a repository set up, the best way to learn about GitHub is their [hello world developer’s guide](https://guides.github.com/activities/hello-world/).

## How GitHub Pages works

GitHub pages allows you to use a specific branch from your repository to host a static website. 

You build and deploy your static site to that branch, and GitHub will serve it for you at `http://username.github.io/repository`.

If you’re using Jekyll, please read the _Using Jekyll with GitHub Pages section_, otherwise move on to _Setting Up Forestry with GitHub Pages_

## Using Jekyll with GitHub Pages

Jekyll is built by GitHub, and due to this you can use Jekyll with GitHub pages:

1. You can let GitHub built your Jekyll site from your `master` source branch \*
2. You can create another branch and manually build your site there.

\* The only caveat with option 1 is that you can only use GitHub support Jekyll plugins. [See the full list](https://pages.github.com/versions/).

## Using method 1

If you are using method one, then all you need to do is enable GitHub pages for your master branch which contains the source files for your Jekyll site.

GitHub will build your Jekyll site each time a new commit happens and serve it automatically.

This requires the GitHub pages gem, which you can add by editing your `Gemfile`, and adding the following line:

    gem "github-pages", group: :jekyll_plugins

Also, please ensure that your `Connection` is set to `Commit to source repo only` in the `Hosting` tab of your site's settings.
_This is to prevent automatically overwriting your source code with your built site._

## Using method 2

If you are using non-whitelisted Jekyll plugins, or have additional steps to your build process that GitHub pages doesn’t support, proceed to the next section.

## Setting Up Forestry for GitHub Pages

To deploy a static site to GitHub pages using Forestry, you must first set up a new branch named `gh-pages` on your repo, which you can do by going to your repository in GitHub and using the branch management dropdown.

![](/docs/assets/images/github-gh-pages-settings.png)

Once your new branch is created, head to the `Settings` page in your site in Forestry, select the `Hosting` tab.

![](/docs/assets/images/forestry-gh-pages-settings.png)

From here you must select GitHub pages from the dropdown menu, choose your repository, and select the new branch. From here on, every time you publish a page we’ll build your site and deploy to this branch.

### Enable GitHub Pages

To have GitHub pages begin serving from your new branch, go to the `Settings` page of your repository and scroll down to the `GitHub Pages` section.

Then select the branch that contains your built static site and click on the Save button.

![](/docs/assets/images/branch-management.png)

Your site should now be served at `http://username.github.io/repository`.