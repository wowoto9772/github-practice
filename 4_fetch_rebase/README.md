# Check current remote

You can know your own remote.

```bash
git remote -v
```

Then you can get whole remote which registered, like below.

```bash
origin  git@github.com:<your-account>/github-practice.git (fetch)
origin  git@github.com:<your-account>/github-practice.git (push)
```

# Add remote url from your forked repo

```bash
# git remote add <remote-name> <remote-url>
git remote add wowoto https://github.com/wowoto9772/github-practice.git
```

Now, you can use the remote wowoto.

# Fetch on registered remote

```bash
git fetch wowoto
```

You can get latest version of wowoto remote's.  
You can adjust wowoto remote' if you want to use.

# Get latest wowoto' branch to your own.

Create temporary-branch for next.

```bash
git checkout -b temp-branch-for-rebase
```

You can get wowoto remote' add-new-4-dir branch' contents.

```bash
# git rebase remote' branch (your branch)
git rebase wowoto/add-new-4-dir
```

And you can get the message,  
"Successfully rebased and updated refs/heads/temp-branch-for-rebase."

If you can skip the (your branch name),  
then adjust your current branch.

And, you can get new commit which message is,  
"Add new-item.txt for rebase scenario".

```bash
git log
```