# Some useful tips reagrding `.[n]vimrc` and Vimscript

## Changing the color of an Highlight group

```viml
highlight <group> cterm=X ctermfg=X ctermbg=X gui=X guifg=X guibg=x
```

## List all the highlight groups

```viml
:hi[ghlight]
```

## List all syntax groups

```viml
:syntax
```

## Get a group color dynamically from a theme

```viml
let fgcolor=synIDattr(synIDtrans(hlID("Normal")), "fg", "gui")
                                        |           |    |_ cterm/gui
                                        |           |_ fg/bg
                                        |_ group name
```

## Shared vim info between vim instances

In `vim` it's called `viminfo`, for `neovim` it's called _shared data_ `ShaDa`.

See `:h viminfo/shada`

## Timetravel

`:h earlier/later`

## Text alignment

`%` means the whole file, you might not need it

`:%ri(ght)` `:%ce(nter)` `:%le(ft)`

## Search for a file in a tree

Will search `CWD` for `<FILENAME>` & keep going up until it finds it/or not

```vim
findfile('<FILENAME>', expand('%:p').';')
```

## Setting an option using a variable

Lets say you have `g:FOO_BAR` that you want to use to set a variable, you have
two options

Option 1:

```vim
let &option = g:FOO_BAR . 'something'
```

Option 2:

```vim
execute 'set option=' . g:FOO_BAR . 'something'
```
