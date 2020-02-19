# Git

## Config types

There are 3 configuration levels in git:

- local - for a repo
- global - for a user
- system - for all users

There are formatted as TOML files - similar to YAML except they have headings like `[heading]`.

## Editing configs

### Local

```bash
$ git config -e --local
```

### Global

```bash
$ git config -e --global
# OR
$ nano ~/.gitconfig
```

## Sample configs

### Local

Here, a template file is referenced. This is useful to prepopulate the commit message and is useful both for command-line commits and for the VS Code commit message.

Note that it is a good idea to keep the template outside of version control, as below. For my case, I want to edit a template with a Jira ticket number while working on a ticket and then I write over the message with something else for another ticket, but no one else needs to have the template file so it is not in version control.

```toml
[commit]
        template = /home/michael/commit_template.txt
```

Note if you are in the repo and the template does not exist, you will get an error message on committing.

### Global

```toml
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
    
[credential]
    # If using HTTPS rather than SSH to push/pull, then this setting keeps your password
    # in memory for a set time, so you are not prompted to enter it again within that period.
    # The time is in seconds so this is 1 hour.
    helper = cache --timeout=3600
```

## Global ignore file

The section above references a global git ignore file, which you can create by follow this section.

Create a file of files for git to ignore globally for you user. The filename is only be convention and needs to be referenced in the config settings as set above.

```bash
$ nano /home/michael/.gitignore
```

Include whatever is relevant for you.

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

# Spyder project file.
.spyderproject
.spyproject
```
