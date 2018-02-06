# Sublime Main Settings

This file is a reference for general settings in Sublime 3, aimed at
a Python developer who also uses other languages.


## Instructions

1. click `Preferences`
2. click `Settings`
3. edit `Preferences.sublime-settings - User` (do not edit the '... Default' file)
4. save (no need to restart Sublime)


## Notes

For more info on specific setting in this file, see the Default settings file in Sublime which is also shown using step 2 above.

Note that comments _are_ allowed in the settings file as of _Sublime version 2_, even though that is not a normal JSON feature. Note however that when changing the font size anywhere in Sublime by holding CTRL and using the mouse scroll, the font size will be updated in the User settings file and _all_ comments will be lost. Therefore, do not keep permanent info there, or use `"_comment"` as a key, as recommended here:

[https://stackoverflow.com/questions/244777/can-comments-be-used-in-json](https://stackoverflow.com/questions/244777/can-comments-be-used-in-json)


## Sample

Comments are included below for readability as a reference file, rather than an implemented file.

```
{
    // ******************
    // Editing and saving
    // ******************

    // A newline character is recommended in scripting, especially for
    // for Bash or Python.
    "ensure_newline_at_eof_on_save": true,

    // Press tab to get 4 spaces instead of tab character. Recommended
    // for Python.
    "translate_tabs_to_spaces": true,

    // This is good to keep your scripts clean by hiding empty spaces at the
    // end of lines. Be careful when using this on someone else's code though,
    // as when you check the file with `git diff` you may see many trivial
    // white changes which could make the number of lines changed large.
    "trim_trailing_white_space_on_save": true,


    // ******************
    // Readability
    // ******************

    "font_size": 11,

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

    // ******************
    // Auto complete
    // ******************

    // Use these in conjunction with the Anaconda plugin.
    "auto_complete_commit_on_tab": true,
    "auto_complete_delay": 1500
}
```