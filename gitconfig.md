[user]
	name = RubenGuerrero
	email = yo@rubenguerrero.com

[core]
	autocrlf = false
	excludesfile = **GITIGNOREGLOBAL_URI**
	editor = vim

[credential "https://github.com"]
	username = RubenGuerrero
	

[alias]
	newb = !git checkout -b $1

	list- = !git log origin/$(git rev-parse --abbrev-ref HEAD)..$(git rev-parse --abbrev-ref HEAD)
	pull- = !git pull origin $(git rev-parse --abbrev-ref HEAD)
	push- = !git push origin $(git rev-parse --abbrev-ref HEAD)

	view-ignore- = !git ls-files -v|grep '^h'

	master = !git checkout master && git pull
	develop	= !git checkout develop && git pull

	master-	= !git checkout master
	develop- = !git checkout develop

	bran = ! ( git checkout master && git pull && git branch $1 ) && git checkout $1
	uncommit = !git reset --soft HEAD~1
	ls = log --pretty=format:"%C(yellow)%h%Cred%d\\ %Creset%s%Cblue\\ [%cn]" --decorate
	ll = log --pretty=format:"%C(yellow)%h%Cred%d\\ %Creset%s%Cblue\\ [%cn]" --decorate --numstat
	lnc = log --pretty=format:"%h\\ %s\\ [%cn]"
	lds = log --pretty=format:"%C(yellow)%h\\ %ad%Cred%d\\ %Creset%s%Cblue\\ [%cn]" --decorate --date=short
	ld = log --pretty=format:"%C(yellow)%h\\ %ad%Cred%d\\ %Creset%s%Cblue\\ [%cn]" --decorate --date=relative
	le = log --oneline --decorate

	dlc = diff --cached HEAD^

	cp = cherry-pick

	st = status -s
	cl = clone
	ci = commit
	co = checkout
	br = branch 
	diff = diff --word-diff
	dc = diff --cached

	graph = log --graph -10 --branches --remotes --tags  --format=format:'%Cgreen%h %Creset• %<(75,trunc)%s (%cN, %cr) %Cred%d' --date-order
	precommit = diff --cached --diff-algorithm=minimal -w
	
[gui]
	encoding = utf-8
[push]
	default = simple

