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

### If the folder is checked into the repo

```sh
git checkout main -- folder_name
```

### If the folder is git ignored

After removing all the files with `git rm -rf .` The folder will still have the ignored files and folders in it. Remove all that are not the one you want to publish. Then unpack the folder by coping it's contents into the root of the repo.

```sh
rm random_file_in_gitignore
cp -r folder_name/* .
rm -rf folder_name
```

## Don't forget to commit and push

```sh
git add .
git commit -m "Publishing to branch_name"
git push origin branch_name
```

???+ note
    If you are deploying to gh-pages with a custom domain you will need a `CNAME` file in the root of this directory. You can create it with `echo "domain.com" > CNAME` and then commit and push it. Make sure you copy it over every time you publish.