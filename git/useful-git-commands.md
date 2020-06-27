# Useful Git Commands

## Clone a repo
`git clone repoURL`

## Create a branch
`git checkout -b branchName`

## Checkout a commit

`git checkout bc90f2cbc9dc4e802b46e7a153aa106dc9a88560`


## Delete a local branch
`git branch -d branchName`

## Add only modified file
`git add -u`

## Commit and add in one-line
`git commit -am fileName`

## View changes
`git diff`

## Check status of git
`git status`

## View history of commits
`git reflog`

## Add all files/directory
`git add .`


##############################
## Switch to develop branch
`git checkout develop`

## Merge friend_groups branch to develop
`git merge --no-ff friend_groups`

## Push changes to remote repository
`git push origin develop`
###############################


## Branch strategy
https://nvie.com/posts/a-successful-git-branching-model/


## Handling merge conflicts
https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/about-merge-conflicts


## Git for Data Science
When working on model parameters, commit each update of the parameters and include the score to more easily revert to a commit for a given model configuration. Additional notes here:
[How to version control your production machine learning models](https://algorithmia.com/blog/how-to-version-control-your-production-machine-learning-models)


