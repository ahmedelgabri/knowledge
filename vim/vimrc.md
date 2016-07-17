# Some useful tips reagrding `.[n]vimrc` and Vimscript

## Changing the color of an Highlight group

```viml
highlight <group> cterm=X ctermfg=X ctermbg=X gui=X guifg=X guibg=x
```

## List all the highlight groups

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

`:%ri(ght)`
`:%ce(nter)`
`:%le(ft)`
