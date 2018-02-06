# Anaconda

Settings for the Sublime _Anaconda_ plugin.


## Instructions

1. click `Preferences`
2. click `Package Settings`
3. click `Anaconda`
4. click `Settings - User`
5. edit
6. save (no need to restart Sublime)


## Notes


For more details, see the Default of the file.


## Sample

Try some of these settings. Some are commented out but already set to a value different to the default.

```javascript
{
    // ***************
    // Linting
    // ***************

    "anaconda_linting_behaviour": "save-only",


    // ***************
    // Auto completion
    // ***************

    /*
        Disable anaconda completion
    */
    //"disable_anaconda_completion": true,

    /*
        Set those as true if you don't want Sublime Text regular completions
    */
    //"suppress_word_completions": true,
    //"suppress_explicit_completions": true,

    /*
        If true, anaconda will add function and class parameters to its
        completions.
    */
    //"complete_parameters": true

    /*
        If true, add all the possible parameters
        If false, add only required parameters
    */
    //"complete_all_parameters": true,
}
```
