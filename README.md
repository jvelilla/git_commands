"# git_commands" 
List of the most useful Git commands that will be available via EiffelGit library.

Git command auto-completion using [ohmyzsh](https://github.com/ohmyzsh/ohmyzsh) on Linux based Systems.

# Status
    - [git status](https://initialcommit.com/blog/git-status)
    - to check on the state of you current directory.

# Stash
    - [git stash](https://git-scm.com/docs/git-stash)
    - https://git-scm.com/book/en/v2/Git-Tools-Stashing-and-Cleaning
    - [tutorial](https://git-scm.com/docs/git-stash)
    - Allows you to go back to the head of a directory and keep your changes.
    - Useful when you want to keep code wihtout committing it.
    - Get a clean working directory.

## Example
Go to the `src` folder and edit the `APPLICATION` class, add a the following line of code to `make`

```
    print ("Hello Eiffel")
```

### How to save this work in progress file without committing?

### Option without label.
```
> git stash
> Saved working directory and index state WIP on main: a3dd7f4 Updated Readme file
```

Now if you check the class APPLICATION, the changes are not anymore.

To retrieve your stashed files you can do.
```
> git stash pop
```
it will retrieve the latest stashed work, the stash work at index 0. 

### Option with label.
If you have multiple stashes is convenient to label them so it's easier to manage the stashes.

```
> git stash save "add: print to creation procedure make"
>Saved working directory and index state On main: add: print to creation procedure make
```

### Listing Stashes
```
> git stash list
>stash@{0}: On main: add: feature fun
>stash@{1}: On main: add: print to creation procedure make
```
It will list the existing stashes indexed by zero.

### Retrieve an stash from the list of stashes
if you want to retrive one of them, just use the following command

```
>git stash apply 1
```
Apply the work done stash at index 1.

### To remove a stash entry from the list

```
git stash drop 0
```
I will remove the stash at index 0, if the list is empty you will get an error like this. The same issue applies if you try to drop an index that doesn't exit.
```
error: refs/stash@{0} is not a valid reference
```
### Check Stash diff

TO check the differences between a stash entry an the last commit you can execute

```
git stash show
```
This one will show a short summary comparing the last commit, with the most recent stash entry. If you want a detailed summary you will need to use

```
git stash show -p
```

And if you want an specific stash entry 

```
git stash show 2 -p
```
Where two is the 2 entry in the list of stashes.


## Staging
The staging area is a (temporary)place to record things(changes) before committing.

    - https://initialcommit.com/blog/git-add

## How to add Changes to Git.
Use `git status` to check your changes to the repository.

The `git add` command can be used to stage one file, multiple files, or stage changes in an entire directory.
```
git add .
```
This will add everything to the staging.

```
git add specific_file
```
This will add the `specific_file` to the staging are.
To revert this, you can execute 
```
git reset specific_file
```
```
git commit -am "message"
```
This will add and commit at the same time.


Adding changes in a granular way using the following command

```
git add -p
```
It will show you all the chanages one by one, asking you if you want to add them. you can answer with Y(yes) or N(no).

Allows us to interactively choose which chunks of code to stage for a commit, allowing us to break our commits up into more reasonable sizes. In this way we can commit the bits of changes within a file that we need, instead of all the changes in the file at once.


### Excercise

1. Add changes to multiple files.
2. Add part of the changes
3. Finally commit.



