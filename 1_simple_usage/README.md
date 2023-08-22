# Make untracked

Generate 1 file.  
This git dosen't know this new file.

```bash
echo "This file is untracked" >> untracked.txt
```

# Check status

```bash
git status
```

Then you may get, below.

```bash
Untracked files:
  (use "git add <file>..." to include in what will be committed)
	untracked.txt
```

# Commit

First, you should add untracked.txt.
```bash
git add untracked.txt
```

And you can commit with message.

```bash
git commit -m "Add untracked.txt in 1_simple_usage"
```

And you can get, below.
```bash
[main ???????] Add untracked.txt in 1_simple_usage
 1 file changed, 1 insertion(+)
 create mode 100644 1_simple_usage/untracked.txt
```