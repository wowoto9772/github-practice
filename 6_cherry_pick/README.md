# Add known commit with commit-id

There is a addtional commit wowoto' 6-cherry-pick-usage branch.  
And the commit id is 5181dbf. So, you can add this commit for your branch.

For cherry-pick test, you may make a new branch for test.

```bash
git checkout -b 6-cherry-pick-test
```

And do use cherry-pick, now.

```bash
git cherry-pick 5181dbf
```

Now, you can know already_known.txt in this folder.

You can forget the commit with 2 options.

1. with git reset version.

```bash
git reset --soft HEAD~1
# and set unstaged for already_known.txt
git reset HEAD ./already_known.txt
```

2. just checkout branch version.

```bash
git checkout main
```