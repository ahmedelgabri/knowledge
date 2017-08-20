You can change the colors of the `ls` output by setting the `$LS_COLORS` env variable & then us `dircolors` command to set it.

### Check the current value of `LS_COLORS`

```sh
$ dircolors -p
```

### Set your own colors

1. `man dircolors` to check colors & syntax
2. add this to your `.zshrc` file

```sh
$ eval $(dircolors path/to/your/LS_COLORS) # name can be anything
```

##### Interesting projects to check:

- https://github.com/trapd00r/LS_COLORS
- https://github.com/ogham/exa
- https://github.com/supercrabtree/k



