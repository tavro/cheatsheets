# cheatsheets

## git (operations)

### squashing
#### what is squashing?
squashing is when you squash two or several commits into one commit to make the branch cleaner

#### example

let's say you have a commit log looking like this with commit messages in commit B through D
making the log look 'unprofessional'

┌───────┐&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;┌───────┐&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;┌───────┐&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;┌───────┐<br/>
│ Commit A │◄─│ Commit B │◄─│ Commit C │◄─│ Commit D │<br/>
└───────┘&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└───────┘&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└───────┘&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└───────┘

then you could squash commit A through D and get something that looks like this

┌───────┐<br/>
│ Commit A │<br/>
└───────┘

#### how to squash already pushed commits
```
git rebase -i HEAD~X
```
where X is the amount of commits you want to include (from HEAD and backwards)

after running this git command you will get to choose what to squash
```
pick commitid1 Commit A
pick commitid2 Commit B
pick commitid3 Commit C
pick commitid4 Commit D
```

in the example case above you would want to do the following
```
pick commitid1 Commit A
squash commitid2 Commit B
squash commitid3 Commit C
squash commitid4 Commit D
```
