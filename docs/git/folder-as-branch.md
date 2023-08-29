# Folder as Branch

## Creating the branch

The most simple way to do is is to orphan a branch and then delete it's contents, then checkout the folder from the main branch and push.

???+ note

    Orphaning a branch is a way to create a branch without a history. It is useful for creating a branch that is not related to the main branch.


```sh
git checkout --orphan branch_name
git rm -rf .
```

## Populating and publishing the branch

```sh
git checkout main -- folder_name
git add .
git commit -m "Publishing to branch_name"
git push origin branch_name
```