# Flake8

Settings for the Sublime _Python Flake8 Lint_ plugin.


## Instructions

1. click `Preferences`
2. click `Package Settings`
3. click `Python Flake8 Lint`
4. click `Settings - User`
5. edit
6. save (no need to restart Sublime)

For more details, see the Default version of the file. See also `Key Bindings - User`.


## Sample

```javascript
{
    // Disable linting on save. Linting can be run manually using the
    // key binding, which is CTRL+ALT+F8 by default.
    "lint_on_save": false,

    // Set to false to prevent verbose pop-up. Then you can rely on the
    // error info at the bottom of the screen, when selecting a line
    // marked with a lint error.
    "popup": false
}
```
