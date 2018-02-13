# Main Settings

This file is a reference for general settings in _Sublime 3_, aimed at
a Python developer who also uses other languages.


## Instructions

1. click `Preferences`
2. click `Settings`
3. edit `Preferences.sublime-settings - User` (do not edit the '... Default' file)
4. save (no need to restart Sublime)


For more info on specific setting in this file, see the `- Default` settings file in Sublime which is also shown when viewing `Settings`.


## Notes

Note that comments _are_ allowed in the settings file as of _Sublime 2_, even though that is not a normal JSON feature. Note however that when changing the font size anywhere in Sublime by holding CTRL and using the mouse scroll, the font size will be updated in the User settings file, the User settings file will be sorted by key alphabetically and _all_ comments will be lost. Therefore, do not keep permanent info there, or use `"_comment"` as a key, as recommended [here](https://stackoverflow.com/questions/244777/can-comments-be-used-in-json) on StackOverflow.


## Sample

Comments are included below for readability as a reference file, rather than an implemented file.

```javascript
{
    //
    // Indentation
    //

    // Set to false to disable detection of tabs vs. spaces on load.
    // I don't know yet if this affects existing or new tabs created in the document, but
    "detect_indentation": false,

    // Press tab to get 4 spaces instead of tab character. Recommended
    // for Python.
    "translate_tabs_to_spaces": true,

    // Set visibility of the indent guide.
    // The default value of ["draw_normal"] only draws vertical dotted lines side by side at each indentical level.
    // Add the "draw_active" option to make the indentation level for the keyboard cursor clear with highlighting.
    // Or make this empy list to disable the indent guide lines.
    "indent_guide_options":
    [
        "draw_normal",
        "draw_active"
    ],


    // ******************
    // White space
    // ******************

    // Determines what character(s) are used to terminate each line in new files.
    // Valid values are 'system' (whatever the OS uses), 'windows' (CRLF) and
    // 'unix' (LF only).
    "default_line_ending": "unix",

    // A newline character is recommended in scripting, especially for
    // for Bash or Python.
    "ensure_newline_at_eof_on_save": true,

    // Remove white space on the end of a line.
    // This is good to keep your scripts clean by hiding empty spaces at the
    // end of lines. Be careful when using this on someone else's code though,
    // as when you check the file with `git diff` you may see many trivial
    // white changes which could make the number of lines changed large.
    // Note that this not apply to text files such as .txt or .md extesions.
    //
    // Highlight all cases of a single space at the end of a line:
    // (there is probably a better way to do this with regex)
    // 1. ctrl+F, or `Find`, `Find...`,
    // 2. press spacebar
    // 3. Enter a new line character by pressing ctrl+enter. This may have indented to a new 
    // line with space after it, so press backspace to remove the extra white space.
    // 4. Press enter button or Find.
    "trim_trailing_white_space_on_save": true,


    //
    // Text Readability
    //

    // Customise this here as required. Alternatively, use ctrl button with the mouse wheel.
    // If find that 13 and 12 are close in size, but 13 looks bold so I use that.
    "font_size": 13,

    // If this is true, lines will always wrap, rather than being hidden
    // and requiring horizontal scrolling to be seen. Note that the wrapping
    // will adjust to the current width of pane and will changes for example
    // if viewing files side by side, or reducing the size over the overall
    // window.
    // This setting works well when wrap_width is off, its default setting
    // at `0` characters.
    "word_wrap": true,

    // 79 is good for Python and 119 is a good alternative for other languages.
    "rulers":
    [
        79,
        119
    ],


    //
    // Auto complete
    //

    "auto_complete_commit_on_tab": true,
    "auto_complete_delay": 1500


    //
    // Editor
    //

    // Use 'Open Folder...' or a drag and directory to Sublime to open the FOLDERS pane. Then set this 
    // true to bold the directory names.
    "bold_folder_labels": true,

    // Makes tabs with modified files more visible
    "highlight_modified_tabs": true,

    // Display file encoding in the status bar
    "show_encoding": true,

    // remember_full_screen will allow Sublime Text to start in full screen
    // mode if it was exited in full screen mode.
    "remember_full_screen": true,

    // Enable spellcheck on a document with F6.
    // Right click and add a word to dictionary if you want it to be recognised.
    // This list below will be created automatically but you can manage it manually.
    // Below are some useful terms to not raise a spellcheck error on.
    "added_words":
    [
        "Debian",
        "Ubuntu",
        "admin",
        "analyse",
        "analysing",
        "app",
        "argparse",
        "conf",
        "config",
        "cron",
        "daemonise",
        "dir",
        "frontend",
        "gitignore",
        "gzip",
        "hashtag",
        "hashtags",
        "html",
        "iterable",
        "nginx",
        "param",
        "readme",
        "repo",
        "repos",
        "sqlobject",
        "sudo",
        "systemctl",
        "systemd",
        "timestamp",
        "unflag",
        "unicode",
        "username",
        "usernames",
        "versioned",
        "virtualenv"
    ]
}
```
