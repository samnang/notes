# Vim Notes

This is a collection of vim notes.

## Vim Visual Mode

* `v%` if the cursor is on the starting/ending parenthesis
* `vib` if the cursor is inside the parenthesis block
* `vi"` for double quotes
* `vi'` for single quotes
* `vi{` / `viB` for curly block
* `gv` Reselect last visual selection

## Indenting
* `==` indents current line
* `=` in visual mode, indents the selected block
* `gg=G` go to beginning of the buffer (gg) and indents (=) until the end of buffer (G)
* `<` and `>` indents a block (in visual mode) to left or right. Press '.' to repeat last indenting and 'u' to undo. 

## Smart movements

* `*` and # search for the word under the cursor forward/backward.
* `w` to the next word
* `W` to the next space-separated word
* `b` / `e` to the begin/end of the current word. (B / E for space separated only)
* `gg` / `G` jump to the begin/end of the file.
* `%` jump to the matching { .. } or ( .. ), etc..
* `{` / `}` jump to next paragraph.
* `'.` jump back to last edited line.
* `nG` jump to line n
* `L` jump to the bottom of the screen (“low”)
* `H` jump to the top of the screen (“high”)
* `M` jump to the middle of the screen (“middle”)
* `C-o` jump back
* `C-i` jump forward
* `zt` move this line to the top of the screen (“top”)
* `zb` move this line to the bottom of the screen (“bottom”)
* `zz` move this line to the middle of the screen (“ziddle?”)

## Finding and Replacing

* `/search_pattern` Find next match. Examples "/function" or "/\d\{2}-\d\{2}-\d\{2}" to locate some date like "1981-06-13"
* `?search_pattern` Find match backward.
* `n` repeat the next '/' or '?' command.
* `N` same as 'n' but in reverse direction.
* `%s/text/other/` Replace 'text' by 'other' in the whole document (some commands accepts ranges and % stands for the whole document range - see ':h range')
* `:s/text/other/` Replace 'text' by 'other' in the current line. Actually, any character can be used instead of '/', like 's.7/11/2010.11/7/2010.'
* `:'<,'>s/text/other/` Replace 'text' by 'other' in the last visual selection. '< and '> are the markers for the beginning and ending of the visual selection. Pressing ':' while on visual mode, these markers are automatically inserted in the command line.
* `&` repeat last substitution command

## Quick editing commands

* `I` insert at the begin.
* `a` / `A` append to next / append to end.
* `o` / `O` open a new line after/before the current.
* `v` / `V` visual mode (to select text!)
* `Shift+R` replace text
* `C` change remaining part of line.
* `dd` delete current line (actually, moves it to Vim internal clipboard)
* `D` delete until the end of the line
* `x` or Delete deletes a character under cursor
* `dw` delete from current cursor until the end of the word under cursor
* `diw` delete inner word (the entire word under the cursor)
* `db` delete until the beginning of the word or a word backward if the cursor is already in the beginning of some word
* `ds'`, `ds"`, `ds{`, `ds[`, `ds(` delete surrounds ('', "", {}, (), [])
* `dst` delete surrounding tag
* `di'`, `di"`, `di{`, `di[`, `di(` delete content inside the given surround
* `da'`, `da"`, `da{`, `da[`, `da(` delete all content of the given surround, including the surround characters
* `dit` delete inner tag content
* `cs` works like `ds`, but replacing the surround instead of deleting them. For instance, ci"' will turn "text" into 'text'. `ci"t<div>` will result in `<div>text</div>`...
* `yss*` apply surround around the entire line. Ex. `yss'` will apply an apostrophe around the line, while `yss<div>` will surround the line with a div tag.
* `s*` adds a surround while on visual mode (click and drag with mouse or press 'v' to ender visual mode and use the movement commands)
* `ys<movement command>` applies surround around the region described by the movement command. Ex. With cursor under "word" `ysiw<span>` results in `<span>word</span>`
* `C`, `cw`, `ciw`, `cb`, `ci*`, etc Works like the delete commands but finish the command on insert mode (c stands for change)
* `\c<space>` toggle line (or block in visual mode) commenting
* `ggdG` [d]eletes entire buffer - from beginning [gg] to end [G] of the document

## Combining commands

* `cW`  = change till end of word
* `3cW` = change 3 words
* `BcW` = to begin of full word, change full word
* `ciW` = change inner word.
* `ci"` = change inner between ".."
* `ci(` = change text between ( .. )
* `4dd` = delete 4 lines
* `3x`  = delete 3 characters.
* `3s`  = substitute 3 characters.

## Folding

* `:set foldmethod=syntax` fold by syntax definitions.
* `:set foldmethod=indent` fold by indentation.
* `zc`	Close the current fold
* `zo`	Open the current fold
* `zM`	Close all folds
* `zr`	Open one level of folds
* `zR`	Open all folds
* `zj`	Move to the next fold
* `zk`	Move to the previous fold
* `zm`	Close one level of folds
* `zn`	Disable folding
* `zN`	Re-enable folding

## Useful programmer commands

* `r` replace one character (e.g. rd replaces the current char with d).
* `~` changes case.
* `J` joins two lines
* `Ctrl+A` / `Ctrl+X` increments/decrements a number.
* `.` repeat last command (a simple macro)
* `=` indent line (specify a range, or use visual mode)

## Macro recording

* Press `q[` key `]` to start recording.
* Then hit `q` to stop recording.
* The macro can be played with `@[` key `]`.

## References
* <http://rosenfeld.heroku.com/en/articles/2010-12-26-achieving-productivity-with-vim-as-ide>
