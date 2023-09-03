# Replace multiple commits as just 1 commit.

Add new branch for this scenario.

```bash
git checkout -b 7-rebase-interactive-squash
```

From now on, add 3 commits like below.

```bash
echo "1" >> squash.txt
git add squash.txt
git commit -m "Add first scenario for squash"

echo "2" >> squash.txt
git add squash.txt
git commit -m "Add second scenario for squash"

echo "3" >> squash.txt
git add squash.txt
git commit -m "Add third scenario for squash"
```

Now, you can check these commits.

```bash
git log
```

And, you can check the results.

```bash
commit ?????? (HEAD -> 7-rebase-interactive-squash)
Author: wowoto9772 <csjaj9772@gmail.com>
Date:   Sun Sep 3 21:47:42 2023 +0900

    Add third scenario for squash

commit ??????
Author: wowoto9772 <csjaj9772@gmail.com>
Date:   Sun Sep 3 21:47:42 2023 +0900

    Add second scenario for squash

commit ??????
Author: wowoto9772 <csjaj9772@gmail.com>
Date:   Sun Sep 3 21:47:12 2023 +0900

    Add first scenario for squash
```

And, you can merge like with rebase interactive mode.

```bash
# only for these 3 commits.
git rebase -i HEAD~3
```

And, you can see this.

```bash
pick ?????? Add first scenario for squash
pick ?????? Add second scenario for squash
pick ?????? Add third scenario for squash

# Rebase ???...??? onto 9e10bec (3 commands)
```

And you should change like this.

```bash
pick e4b0b9b Add first scenario for squash
s 1f45d52 Add second scenario for squash
s 4784371 Add third scenario for squash
```

And you can merge 3 commits as one.
```bash
# This is a combination of 3 commits.
# This is the 1st commit message:

Add first scenario for squash

# This is the commit message #2:

Add second scenario for squash

# This is the commit message #3:

Add third scenario for squash
```

And, this "s" means squash.

# Change the orders of commits.

Please make another branch for this scenario.

```bash
git checkout -b 7-rebase-interactive-change-order
```

And, you can add 3 commits like below.

```bash
echo "1" >> change_order.txt
git add change_order.txt
git commit -m "Add first scenario for change order"

echo "2" >> change_order-2nd.txt
git add change_order-2nd.txt
git commit -m "Add second scenario for change order"

echo "3" >> change_order-3rd.txt
git add change_order-3rd.txt
git commit -m "Add third scenario for change order"
```

And, you can change orders of commits.

```bash
git rebase -i HEAD~3
```

If you change the commit like below, then order is changed.

```
pick fa053a0 Add first scenario for change order
pick a2db145 Add third scenario for change order
pick 957cc14 Add second scenario for change order
```