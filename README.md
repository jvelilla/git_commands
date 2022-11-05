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

Option1
> git stash