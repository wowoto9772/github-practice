# Git conflict during stash

Please make the branch for conflict test.

```bash
git checkout -b 5-test-stash-err
```

And, you just add line to stash_err.txt.

```bash
echo "Now, stash conflict is occurred." >> stash_err.txt
git diff
```

If we have to get new branch's contents,
Then, stash is required.

```bash
git stash
git rebase wowoto/5-occur-stash-err
```

And, you can stash pop your previous saved.

```bash
git stash pop
```

And, you can know the conflicts by stash pop.

```bash
Auto-merging 5_resolve_conflicts/stash_err.txt
CONFLICT (content): Merge conflict in 5_resolve_conflicts/stash_err.txt
The stash entry is kept in case you need it again.
```

And you can know the details.

```bash
git diff
```

And this is the diffs.

```bash
diff --cc 5_resolve_conflicts/stash_err.txt
index 5d641a4,c001e84..0000000
--- a/5_resolve_conflicts/stash_err.txt
+++ b/5_resolve_conflicts/stash_err.txt
@@@ -1,3 -1,3 +1,7 @@@
  This is the example with using git stash.
  This item maybe problematic for during stash pop.
- New line is added.
 -Now, stash conflict is occurred.
++<<<<<<< Updated upstream
++New line is added.
++=======
++Now, stash conflict is occurred.
++>>>>>>> Stashed changes
```

Now, you should decide to keep both changes, or not.
You can edit in vscode, vim, etc.

![vscode-fix](resources/5_stash_err.png)

And this is the desired when we choose both changes.

```bash
This is the example with using git stash.
This item maybe problematic for during stash pop.
New line is added.
Now, stash conflict is occurred.
```

And after fixed it, you can use for staged.

```bash
git add stash_err.txt

# if you want to set unstaged, then
# use "git reset HEAD stash_err.txt"
```