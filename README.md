# git-cleanup

`git-cleanup` simplifies the process of removing merged and deleted branches.

## Installation

### Arch Linux

* [git-cleanup][aurpkg]

[aurpkg]: https://aur.archlinux.org/packages/git-cleanup

For other distributions, see below.

### Build from source

Obtain the source by cloning [this repository][gh/sudoforge/git-cleanup] or
by downloading the tarball of a [release][gh/sudoforge/git-cleanup/releases].
Then run `make install` from the source root.

```
$ git clone https://github.com/sudoforge/git-cleanup.git
$ cd git-cleanup
```

#### Linux

```
$ [sudo] make install
```


#### BSD (and derivatives like OSX)

```
$ PREFIX=/usr/local make install
```

#### Other

As you can see from above, the standard `PREFIX= make install` pattern is
supported. Plop it anywhere in your `PATH`!

[gh/sudoforge/git-cleanup]: https://github.com/sudoforge/git-cleanup.git
[gh/sudoforge/git-cleanup/releases]: https://github.com/sudoforge/git-cleanup/releases

# USAGE

```
USAGE
    git cleanup [help] [OPTIONS] BRANCH_NAME

ARGUMENTS
    help
        Displays this message. This must be the first argument passed
        to git-cleanup, e.g. 'git cleanup help'

    BRANCH_NAME
        The branch to check against. Defaults to the branch currently checked out.

OPTIONS
    --debug
        Print debugging information

    -c, --confirm
        Ask for confirmation before deleting each merged branch.

    -u REMOTE, --update-remote REMOTE
        Also delete the branch on the specified remote.

INFORMATION
    git-cleanup provides a simple interface for removing merged and deleted
    refs from both local and remote repositories. By default, git-cleanup will
    never remove a ref if any of the following conditions are met:
        - the ref name is 'master'
        - the ref name exists under a 'git-cleanup.keep' entry in a .gitconfig
          file at the system, user, or local scope.
```
