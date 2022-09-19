# Matrix CMS community
A place to document the undocumented bugs and functionality in Matrix and Funnelback.

Want to contribute? [Start a discussion.](https://github.com/matrix-cms-community/matrix-cms-community.github.io/discussions)

## SCSS files
`Matrix v5.5.6.4`
Creating a new SCSS asset and immediately adding one or more @import statements in the parse file (to CSS files that don't exist) will corrupt the SCSS file.

### Workaround
Create your SCSS asset and do nothing until you create at least one CSS file underneath. You can then go back and add your import statement(s).
If you've already made this mistake, try ticking the "Yes, manually reparse the existing file" checkbox and saving.

## Keywords in JS
`Matrix v5.5.6.4`
Matrix keywords will be evaluated within js (if the js is within a container that evaluates js) but cannot be "pieced" together.

For example, something like this won't work:
```
getMetadata('type');

getMetadata: function(machineName) {
  return '%globals_get_id^as_asset:asset_metadata_' + machineName + '%';
}
```

### Workaround
Non-DRY code. Instead of having your repeating code written out once in a function with only the different parts passed to it, you have to repeat every step. Not a big deal in the example above, but it becomes very messy if you want to retrieve data and manipulate it before returning it.


## Git file bridge
`Matrix <v6.8.x`
The default branch in your repo must be named "master". Any other name (eg. "main") will mean you'll not be able to clone the repo into Matrix (either via HTTPS or SSH). [Issue in SquizMap.](https://squizmap.squiz.net/matrix/12552)

### Workaround
Change the default branch to "master" in your git repo.
