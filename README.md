# GitHub Pages Tutorial

## Setting up your repo for the first time
* `mkdir repo-name`
* `cd repo-name`
* `git init`
* `touch index.html`
* `git add index.html`
* `git commit -m "create index"`  


**Create a remote repository on GitHub with the same name**  

* `git remote add origin URL`
* `git push -u origin master`

## Making your gh-pages branch
* use `git branch` to see your branches
  * you should only see `master`
* use `git branch gh-pages` to make a new branch
* now `git branch` should show:

```
  gh-pages
* master
```

## Making your _gh-pages_ and _master_ branches mirrored
* open the hidden file `.git/config`
  * in cloud9, use `c9 .git/config`
* add these two lines in the `[remote “origin”]` section:
```
	push = +refs/heads/master:refs/heads/gh-pages
	push = +refs/heads/master:refs/heads/master
```
* it should now look like:
```
[remote "origin"]
	fetch = +refs/heads/*:refs/remotes/origin/*
	url = git@github.com:user/repo.git
	push = +refs/heads/master:refs/heads/gh-pages
	push = +refs/heads/master:refs/heads/master
```
* save

## Updating your content and pushing
* add content to `index.html`
* `git add index.html`
* `git commit -m "<whatever content you add>"`
* `git push`
* at the bottom of the message, you should see something like:
```
To git@github.com:<your-username>/<your-repo-name>.git
   b33fe26..4854de6  master -> master
 * [new branch]      master -> gh-pages
```

## Previewing your page
* In a new tab, you should see your page running at the following URL:  
`<your-username>.github.io/<your-repo-name>`

---

## Work smarter, not harder
It would be a good idea to save a short reminder of the crucial steps into a text file (such as gh-pages.txt) in the root directory of your workspace.  That way, you don't have to re-visit this tutorial every time you want to mirror with gh-pages.

In cloud9, it looks like this:  

* `touch ~/workspace/gh-pages.txt`
* `c9 ~/workspace/gh-pages.txt`
* Copy/paste the code snippet below

```
***COMMAND LINE***
git branch gh-pages
c9 .git/config

***PASTE INTO REMOTE ORIGIN***
push = +refs/heads/master:refs/heads/gh-pages
push = +refs/heads/master:refs/heads/master
```

---

### Need to delete the `gh-pages` branch?
* Deleting the local branch:
  * `git branch -D gh-pages`
* Deleting the remote branch:
  * `git push origin --delete gh-pages`
  
