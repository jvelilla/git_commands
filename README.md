"# git_commands" 

Git command auto-completion using [ohmyzsh](https://github.com/ohmyzsh/ohmyzsh) on Linux based Systems.

# Status

# Stash
    - [git stash](https://git-scm.com/docs/git-stash)
    - [tutorial](https://git-scm.com/docs/git-stash)
    - Allows you to go back to the head of a directory and keep your changes.
    - Useful when you want to keep code wihtout committing it.

## Example
Go to the `src` folder and edit the `APPLICATION` class add a the following line of code to
`make`
    print ("Hello Eiffel")

### How to save this work in progress file without committing?

### Option without label.
> git stash
> Saved working directory and index state WIP on main: a3dd7f4 Updated Readme file

Now if you check the class APPLICATION, the changes are not anymore.

To retrieve your stashed files you can do

> git stash pop

### Option with label.
If you have multiple stashes is convenient to label them so it's easier to manage the stashes.

> git stash save "add: print to creation procedure make"
>Saved working directory and index state On main: add: print to creation procedure make

### Listing Stashes
> git stash list
I will list the existing stashes indexed by zero.

```
stash@{0}: On main: add: feature fun
stash@{1}: On main: add: print to creation procedure make
```


### Retrieve an stash from the list of stashes
if you want to retrive one of them, just use the following command

>git stash apply 1
