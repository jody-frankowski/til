# Merge two git repos

You can merge two git repos and keep their history in a new one by adding both
their remotes, fetching and merging their desired branches in the new repo:

```sh
mkdir new
cd new
git init
git remote add old-a url://old-a
git remote add old-b url://old-b
git remote fetch old-a
git remote fetch old-b
git merge old-a/master
git merge old-b/master
```
