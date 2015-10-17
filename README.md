# GitHub Pages Tutorial

## Set up your repo:
* `git init`
* `touch index.html`
* `git add index.html`
* `git commit -m "create index"`
* `git remote add origin URL`
* `git push -u origin master`

## Make your gh-pages branch
* use `git branch` to see your branches
  * you should only see `master`
* use `git branch gh-pages` to make a new branch
* now `git branch` should show:

```
  gh-pages
* master
```

## Make your _gh-pages_ and _master_ branches mirrored
* open the hidden file `.git/config`
  * in cloud9, use `c9 .git/config`
* add these two lines in the [remote “origin”] section:
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

## Update your content and push
* add content to `index.html`
* `git add index.html`
* `git commit -m "<whatever content you add>"`
* `git push`
* at the bottom of the message, you should see something like:
```
To git@github.com:<your-username>/<your-repo-name>.git
   68542ca..99a3a46  master -> gh-pages
   68542ca..99a3a46  master -> master
```

## Preview your page
* `<your-username>.github.io/<your-repo-name>`

---

### Need to delete the `gh-pages` branch?
* Deleting the local branch:
  * `git branch -D gh-pages`
* Deleting the remote branch:
  * `git push origin --delete gh-pages`