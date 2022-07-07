# Matrix CMS community
A place to document the undocumented bugs and functionality in Matrix and Funnelback.

Submit your bugs and functionality to: <email address>

## Bugs list
### SCSS files
Matrix v5.5.6.4
If you create a new SCSS asset and immediately add one or more @import statements in the parse file to CSS files that don't exist, this will corrupt the SCSS file.

#### Workaround
Create your SCSS asset and do nothing until you create at least one CSS file underneath. You can then go back and add your import statement(s).
If you've already made this mistake, try ticking the "Yes, manually reparse the existing file" checkbox and saving.
