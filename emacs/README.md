# Emacs

Emacs Reference and Configuration

## Overview

### What is Emacs?

### Why should I use Emacs?
* Amazingly Csutomizable
* Endless room for growth

### How to learn Emacs?
Start with the built-in tutorial `C-h t`(Repaeat as many ties as you need to)

Other good help commands
`C-h i`
`C-h <keyborad-shortcut>`
`C-h f` describes commands/functions
`C-h a` search for commands
`C-h C-h` show help

## Emacs Notation and Lingo
`C-char` Control-char
`M-char` or `Meta-char` If `Alt` key is present, hold down Alt while typing `char`. If no `Alt` key, type `ESC` key and then `char`.
`ESC` Escape key. Generally, any one of `Esc`, `F11`, or `C-[`.

`Kill` Remove from currently active buffer and append to paste buffer. Equivalent to `Cut` in other editors.
`sentence` In a text buffer: anything that ends with a period. In a program buffer: anything enclosed in `()` or `{}` or `[]`.
`window` an on-screen view of a buffer.
`buffer` an in-memory version of a file, or the terminal window for a utility.

## Basic
`C-x C-f` open/find file
`C-x C-s` save a file to disk
`C-x s` save all files
`C-x C-c` quit

## Moving
`C-f` forward one character
`C-b` back one character

`C-n` next line
`C-p` previous line

`C-a` beginning of line
`C-e` end of line

`M-f` forwar one word
`M-b` back one word

`M-a` previous sentence
`M-e` next sentence

`M-v` previous screen
`C-v` next screen

`M-<` beginning of buffer
`M->` end of buffer


`C-u 3 C-p` back 3 lines
`C-u 10 C-f` forward 10 characters
`M-1 M-0 C-f` forward 10 characters
`C-u C-n` forward 4 lines
`C-u C-u C-n` forward 16 lines
`C-u C-u C-u C-n` forward 64 lines

`M-g g` jump to specified line

## Search
`C-s` search forward
`C-r` search backwards
`C-M-s` regular expression search
`C-M-r` reverse regular expression search

`M-p` select previous search string
`M-n` select next later search string
`RET` exit incremental search
`DEL` undo effect of last character
`C-g` abort current search

## Replace
`M-%` replace
`M-x replace-string` replace all
`M-g g` go to line numbner

## Kill and Yank
`C-Space` set mark
`C-x C-x` swap mark and cursor

`C-w` kill region
`M-w` copy

`C-d` delete character
`M-d` kill word
`C-k` kill line

## Mutiple Buffer
`C-x b <buffer-name>` switch to named buffer
`C-x C-b` list all buffers
`C-x k` kill current buffer

`C-x 2` horizontal split
`C-x 5` vertical split
`C-x 1` only show this buffer
`C-x 0` hide this buffer

## Rectangle
`C-x r k` kill rectangle
`C-x r y` yank rectangle
`C-x r d` delete rectangle
`C-x r c` clear rectangle
`C-x r t` replace rectangle with string
`C-x r o` replace rectangle with space

## Shells
`M-!` execute a shell command
`M-&` execute a shell command asynchronously
`M-|` run a shell command on the region
`M-x shell` start a shell in window shell


## Reference
* [GNU Emacs Manual](http://www.gnu.org/software/emacs/manual/emacs.html)
* [A guided Tour of Emacs](http://www.gnu.org/software/emacs/tour/)
* [GNU Emacs Reference Card](http://gnu.org/software/emacs/refcards/pdf/refcard.pdf)
* [Emacs Cheat Sheet](http://www.rgrjr.com/emacs/emacs_cheat.html)
* [Emacs Wiki](http://www.emacswiki.org)
* [Emacs related blogs](http://planet.emacsen.org)
* [Awesome Emacs](https://github.com/emacs-tw/awesome-emacs)
* [Master Emacs in One Year Guide](https://github.com/redguardtoo/mastering-emacs-in-one-year-guide)
* [A reasonable Emacs config by Purcell](https://github.com/purcell/emacs.d)

