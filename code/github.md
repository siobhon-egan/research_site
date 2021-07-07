---
sort: 2
---

# GitHub

source: `{{ page.path }}`


<span class="badge badge-info">Getting started on sharing code</span>


[GitHub](https://github.com/) -  provides hosting for software development version control using Git. It the industry standard, universal platform to share code and collaborate on projects. GitHub offers plans free of charge but you can also upgrade for extra storage and other special features if you need.

Offical GitHub links

* [GitHub Help](https://help.github.com/en)
    - [Quick Start](https://help.github.com/en/github/getting-started-with-github/quickstart)
* [Documenting your projects on GitHub](https://guides.github.com/features/wikis/)

GitHub and RStudio

* [Happy Git and GitHub for the useR](https://happygitwithr.com/)

I **highly** recommend doing the [GitHub lesson](http://swcarpentry.github.io/git-novice/) on software carpentry

## Useful bits

Help
```
git --help
```

Initalize a repo
```
git init
```

Show status of a repo
```
git status
```

Add all files to the staging area
```
git add .
```
Add only certain files to staging area
```
git add filename.txt
```

Save the staged content as a new commit into the local repo
```
git commit -m "message here"
```

Copy changes from a local repository to a remote repository
```
git push origin master
```

Copy changes from a remote repository to a local repository
```
git pull origin master
```

Cloning a repo - make a local copy of a repository
```
git clone https://github.com/repo/name.git ~/Path/here
```

### Workflow for pushing new repo to github

Quick guide for making a new repository on local machine and pushing it to GitHub.

On local machine
```
mkdir directory
cd directory
touch README.md
git init
```

On GitHub make a new repo with the same filename -> make sure you create an empty repository.     
Copy the https link to clip board and go back to terminal on local machine
```
git remote add origin https://github.com/siobhon-egan/repository.git
git remote -v
git add .
git commit -m "first commit"
git push origin master
```

### Workflow for pulling existing github repo

Quick guide for pulling an existing repo from GitHub to local machine.

On local machine
```
mkdir directory
cd directory
git init
```

On GitHub the existing repository in this case is called **directory**.      
Copy the https link to clip board and go back to terminal on local machine
```
git remote add origin https://github.com/siobhon-egan/repository.git
git remote -v
git pull origin master
```


## Git ignore

Some handy git-related functions available in the [usethis](https://usethis.r-lib.org/reference/index.html#section-git-and-github) package.    
In particular `git_vaccinate()` adds *'.Rproj.user', '.Rhistory', '.Rdata', '.httr-oauth', '.DS_Store'* to your `.gitignore` file.

It might be handy to made a global `.gitignore` file to make sure you always ignore certain files (e.g. the `.DS_Store`)

```bash
# make a global .gitignore file
echo .DS_Store >> ~/.gitignore_global
# configure to use this file for all of your repositories
git config --global core.excludesfile ~/.gitignore_global
```