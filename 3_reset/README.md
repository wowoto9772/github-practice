# Change file as unstaged, and restored.

Add simple text to item-org.txt.

```bash
echo "This line may be deleted." >> item-org.txt
```

And you can see the diffs.

```bash
git diff
```

Then you can get, below.

```bash
@@ -1,2 +1,3 @@
 This is original item.
 This item should be preserved.
+This line may be deleted.
```

And change item-org.txt as staged.

```bash
git add item-org.txt
git status
```

And you can restore as unstaged by below cmd.

```bash
git reset HEAD item-org.txt
```

And you can get, below.

```bash
Unstaged changes after reset:
M       3_reset/item-org.txt
```

And you can know, item-org.txt is just modified.

```bash
git status
```

And, you can restore original one.

```bash
git checkout -- item-org.txt
git diff
```

And nothing changed.

# Remove latest commit

Create 1 file and do commit, now.

```bash
touch empty.log
git add empty.log
git commit -m "Add empty.log to 3_reset"
```

And, you can know commited logs.

```bash
git log

# (and quit with q)
```

And, now you can delete your latest 1 commit.  
The commit' message is "Add empty.log ...".

```bash
git reset --soft HEAD~1
```

And, you can know the staged before you commit.

```bash
git status
```

And, make empty.log unstaged.

```bash
git reset HEAD empty.log
```

And, empty.log is just untracked.
