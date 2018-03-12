# Git

There are 3 configuration levels in git:
- local (repo-specific)
- global (user-specific)
- system (system-wide)

How to edit your user's global file, with some of my suggestions.

```bash
$ git config --global -e
# OR
$ nano ~/.gitconfig
```

```bash
# This is Git's per-user configuration file.
[user]
        name = YourName
        email = username@gmail.com
[core]
        editor = nano
        excludesfile = /home/michael/.gitignore

[alias]
    # Some suggested aliases which can be used with the git command.
    
    # Add short output flag.
    st = status -s
    ci = commit
    
    # Add --all and --verbose flags.
    br = branch -av
    co = checkout
    
    # Normally `git diff` only shows unstaged changes. This will
    # show only staged (i.e. cached) changes and uses HEAD
    # as the default <commit> value. 
    dc = diff --cached

    
    # Show diff of staged AND unstaged changes, relative to previous commit.
    dh = diff HEAD
    
    # Shortern to single line for log entry. Note that the -o abbreviation
    # does not exist yet for any log options.
    log -o = log --oneline
    # --patch:
    #    Generate patch i.e. diff for each commit.
    lg = log -p
    # --graph: 
    #     Draw a text-based graphical representation of the commit history on 
    #     the left hand side of the output.
    # --decorate: 
    #     Print out the ref names of any commits that are shown. Defaults to
    #     short optionm such that the name prefixes refs/heads/, refs/tags/ and 
    #     refs/remotes/ will not be printed.
    lol = log --graph --decorate --oneline
    # --all: 
    #    Pretend as if all the refs in refs/ are listed on the command line as <commit>.
    lola = lol --all
    
    # Show information about files in the index and the working tree
    ls = ls-files
    # Show files ignored by git.
    ign = ls-files -o -i --exclude-standard
```

```bash
$ nano /home/michael/.gitignore
```
```bash
# Global .gitgnore file for current user.
#
# Anything here will be ignored across all repos, without
# having to add the rule in each repo's .gitignore file.
# Note however that anyone who clones any of your repos and generates
# files the ones below will NOT have this global .gitignore file.
# So be intentional with what you put here.

# Folder view preferences file in KDE's Dolphin. 
.idea

# Vim's tempory files, which exist while a file is open for editing.
# and should be deleted by the system when the editor is exited.
# They may remain if the editor exits unexpectedly, such that the
# data can recovered.
.swp

# CSV lock file to prevent other applications from editing a CSV
# while it is open.
.~lock*.csv#
```

Note that you could include the following in the above file as well. Though, it appears in a repo's own `.gitignore` file when using Github to auto-generate it, so I think it is appropriate to ignore Spyder projects within a repo's own `.gitignore` file rather than the global file here.
```
# Spyder project file.
.spyproject
```
