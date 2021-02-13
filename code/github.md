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

Cloning a repo
```
git clone https://github.com/repo/name.git ~/Path/here
```
