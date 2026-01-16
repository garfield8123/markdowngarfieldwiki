# VIM editor commands

| Command | Does the following |
| --- | --- |
| Insert Text |  |
| a | Inserts text after the cursor |
| A | Inserts text at the end of the current line |
| I | Inserts text at the beginning of the current Line |
| i | Inserts text before the cursor |
| Delete Text |  |
| D | Delets up the end of the current line |
| dd | Deletes the current line |
| dG | Delets from teh current line to the end of the file |
| dw | Deletes teh current word where teh cursor presently resides |
| x | Deletes the cahracter on which the cursor rests |
| Change Text |  |
| C | Changes up to the end of the current line |
| cc | Changes the current line |
| J | Joins teh current line with the next one |
| rx | Replaces the character under the curosr with x (where x is any character) |
| Move cursor |  |
| h | Moves one character to the left |
| j | Moves one line down |
| k | moves on line up |
| L | Moves to the end fo the screen |
| l | Moves one character to the right |
| w | Moves to the beginning of the following word |
| b | Moves to the beginning of the previous word |
| Scroll text |  |
| Ctrl + D | Scrolls forward through the file by half a screen |
| Ctrl + U | Scrolls backward through the file by half a screen |
| Refresh screen |  |
| Ctrl + L | Redraws the screen |
| Cut and Paste text |  |
| yy | Yanks (copies) the current line to an unnamed buffer |
| P | Puts the yanked line aove the current line |
| p | Put the yanked line below the current line |
| Colon Commands |  |
| :!command | Executes a shell command |
| :q | Quites the editor |
| :q! | Quits without saving changes |
| :r filename | Reads teh file and inserts it after the current line |
| :w filename | Writes a buffer to the file |
| :wq | Save changes and exits |
| search text |  |
| /string | Searches forward for a string |
| ?string | Searches backward for a string |
| Miscellaneous |  |
| u | Undoes the last command |
| Esc | Ends input mode and enters visual command mode |
| U | Undoes recent changes to the current line |