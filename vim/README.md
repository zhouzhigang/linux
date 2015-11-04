# Vim
Vim Reference

## Overview
### What is Vim?

### Why should I use Vim? What can Vim do?

### How to learn Vim?

View vim help by `:help` or `:h vimtutor`.

## Basic
### Different Mode
Normal Mode `ESC`

Insert Mode `i`, `I`, `a`, `A`, `o`, `O`, `s`, `S`

Command Mode `:`

Visual `v`, `V`

Select `m`

## Cursor Movement

### Character(`h`,`j`,`k`,`l`)

       k
    h    l
     j

**NOTE**: can combine with numbers, for example, `5j` means downward 5 lines.

### Word(`w`,`e`,`b`)

`w`or `W` start of word(forward) 

`e`or `E` end of word(forward)

`b`or `B` begin of word(backward)

**Note**: For upppercase letter, it means the words can contain punctuation(punctuation-word example).

### Line(`0`,`$`)
`0` start of line

`$` end of line

`^` first non-blank character of the line

`g_`last non-blank character of the line

  eg: This is a line which has space   

### sentence and paragraph(`{`,`}`)
`(` sentence backward

`)` sentence forward

`{` paragraph backward

`}` paragraph forward

`%` jump to match

### Screen(`Ctrl+u`,`Ctrl+d`,`gg`,`G`,`:N`)
`H` screen top

`M` screen middle

`L` screen botttom


`Ctrl+b` backward one page

`Ctrl+u` up half page

`Ctrl+y` backward one line


`Ctrl+f` forward one page

`Ctrl+d` down half page

`Ctrl+e` forward one line


`gg` begin of file
`G` end of file

`5gg` or `5G` goto line 5


`zt` scroll cursor to top

`zb` scroll cursor to buttom

`zz` scroll cursor to center

## Editing

### Command Pattern

**text-objects**

    `<comand>i<text-objects>` or `<comand>a<text-objects>`

`<command>` can be `c`(change), `r`(replace), `d`(delete), `y`(yank)

`i` means inner, not including space
`a` word including space

`<text-objects>` can be `w`(word), `s`(sentence), `p`(paragraph)

**command repeat count**


### Change(`cw`, `cc`, `c$`)

`c` change character and start insert

`cl` change current character, equals to `x`

`ch` change previous character, equals to `X`


`cb` change to begin of the word

`cw` change to the end of the word

`caw` change current word, include space

`ciw` change current word, not include space

`c3w` change next 3 words


`cf<char>` change to a specified char

`ct<char>` change before a specified char


`cc` change entire line

`c0` change to begin of line

`c$` or `C` change/replace to then end of the line

`cgg` change to begin of the file

`cG` change to end of the file

`~` change between uppercase letter and lowercase letter

### Replace(`r`)

`r` replace a single character, and back to Normal mode

`2rp` replace 2 characters with p

`R` enter Replace mode.

### Delete/Cut(`x`, `dw`, `d$`, `dG`, `dgg`, `J`)

`x` or `dl` delete/cut character

`X` or `dh` delete/cut left character


`db` cut to begin of word

`dw` cut to end of word

`daw` cut word with space

`diw` cut word without space


`dd` cut a line

`2dd` delete/cut 2 lines


`d$` or `D` delete to the end of line

`J` join lines

`2J` join 2 lines

### Yank/Copy and Paste(`yw`, `y$`, `yy`, `p`, `P`)

`yb` yank to begin of word

`yw` yank to end of word

`yiw` yank current word, not include space

`yaw` yank current word, include space


`yy` or `Y` yank/copy a line

`2yy` yank/copy 2 lines

`y$` yank/copy to end of line


`ygg` yank to begin of the file

`yG` yank to end of the file


`p` put/paste the clipboard after cursor

`P` put/paste before cursor

### Undo and Redo(`u`, `Ctrl+r`)

`u` undo

`U` undo all latest changes on one line

`Ctrl+r` redo


## Search and Replace(`/`, `?`, `%s/old/new/g`, `5, 12s/old/new/g`)
`f<char>` forward find a char in current line

`F<char>` backward find a char in current line

`t<char>` till a char in current line

`T<char>` backward till a char in current line


`/pattern` search for pattern

`?pattern` search backward for pattern

`*` forward search current word

`#` backward search current word

`n` repeat search in same direction

`N` repeat search in opposite direction


`:s/old/new/g` replace old with new in current line

`:%s/old/new/g` replace all old with new in current file

`:%s/old/new/gc` replace all old with new in current file with confirmations

`:5, 12s/old/new/g` replace old with new for all lines from 5 to 12

## File Operation(`:e`, `:w`, `:q`, `:q!`)
`:e filename` edit a file in a new buffer

`:w` write file

`:w!` write file(ignoring warnings)

`w! file` overwrite file(ignoring warnings)

`:wq` write file and quite

`:q` quit

`:q!` quit even if changes not saved

`ZZ` or `:x` quie, writing file if file changed

### Mutiple File(`:sp`, `:vsp`, `:bn`, `:bp`, `Ctrl+w+h/j/k/l`)
`:sp <file>` open a file in a new buffer and split window

`:vsp <file>` open a file in a new buffer and svertically plit window

`:bn` or `:bnext` go to the next buffer

`:bp` or `:bprev` go to the previous buffer

`Ctrl+ws` split window

`Ctrl+ww` switch window

`Ctrl+wq` quit a window

`Ctrl+wv` split window vertically

`Ctrl+wh` move cursor to the left window(vertical split)

`Ctrl+wl` move cursor to the right window(vertical split)

`Ctrl+wj` move cursor to the window below(horizontal split)

`Ctrl+wk` move cursor to the window above(horizontal split)


## Plugin

### Plugin Management
* [Pathogen](https://github.com/tpope/vim-pathogen)
* [Vundle](https://github.com/gmarik/Vundle.vim)
* [Neobundle](https://github.com/Shougo/neobundle.vim)

### Common Plugins
* [NERDTree](https://github.com/scrooloose/nerdtree) - A filesystem tree explorer.
* [taglist](https://github.com/vim-scripts/taglist.vim) - Source code browser.
* [NERD_commenter](https://github.com/vim-scripts/The-NERD-Commenter) - A plugin that allows for easy commenting of code.
* [DoxygenToolkit](https://github.com/vim-scripts/DoxygenToolkit.vim) - Simplify Doxygen documentation.
* [YouCompleteMe](https://github.com/Valloric/YouCompleteMe) - A code-completion engine for Vim.
* [ultisnips](https://github.com/SirVer/ultisnips) - The ultimate snipper solution for Vim.
* [vim-snippets](https://github.com/honza/vim-snippets) - vim-snipmate default snippets.
* [delimitMate](https://github.com/Raimondi/delimitMate) - Insert mode auto-completion for quotes, parents, brackets, etc.
* [vim-surround](https://github.com/tpope/vim-surround) - quoting/parenthesizing made simple.
* [vim-repeat](https://github.com/tpope/vim-repeat) - enable repeating supperted plugin maps with ".".
* [vim-quickrun](https://github.com/thinca/vim-quickrun) - Run commands quickly.
* [vim-trailing-whitespace](https://github.com/bronson/vim-trailing-whitespace) - Highlights trailing whirespace in red and provides: FixWhitespace to fix it.
* [vim-easy-align](https://github.com/junegunn/vim-easy-align) - Vim alignment plugin.
* [vim-easymotion](https://github.com/Lokaltog/vim-easymotion) - Vim motions on speed.

## Configuration
Learn form other people's configration.

* [The ultimate vim configuration](https://github.com/amix/vimrc)
* [k-vim by wklken](https://github.com/wklken/k-vim)
* [vim by ma6174](https://github.com/ma6174/vim)


## Some Tips

## Vim Style in other Application
* [Vimium in Chrome](Vimium.md)
* [Vimperator | Pendatactyl in Firefox](vimperator.md)

## Reference
* [Vim Online](http://www.vim.org)
* [Awesome Vim Resources](https://github.com/matteocrippa/awesome-vim)
* [Learn Vim Progressively](http://yannesposito.com/Scratch/en/blog/Learn-Vim-Progressively/)
* [Vim Cheat Sheet - Image](http://www.viemu.com/vi-vim-cheat-sheet.gif)
* [Vim Cheat Sheet - Text](http://vim.rtorr.com)
* [Vim Adventures Game](http://vim-adventures.com)
* [Vundle, the plug-in manager for Vim](https://github.com/gmarik/Vundle)
* [Awesome Vim Plugin Shortlist](https://github.com/akrawchyk/awesome-vim)
* [The ultimate Vim configuration: vimrc](https://github.com/amix/vimrc)
* [Practical Vim: Edit Text at the Speed of Thought](https://pragprog.com/book/dnvim/practical-vim)
* [Vim Tutorial by xbeta - Chinese](http://xbeta.info/vim-tutorials.htm)
* [Learn Vim Together by Edward Lee - Chinese](http://www.study-area.org/tips/vim/)
