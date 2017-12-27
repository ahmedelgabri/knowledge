## Change zsh config directory

By providing setting `$ZDOTDIR` you can change the main zsh config directory to use instead of
`$HOME`, this can be done by setting `$ZDOTDIR` in `~/.zshenv`

```zsh
ZDOTDIR=~/my/config/path
```

Now you can put `.zshrc`, `.zprofile`, etc... inside `~/my/config/path` and everything will work as
expected.

## Override an interactive alias

if you have `rm` to be aliased to `rm -i` _which you should anyway_ & you want to use `rm` in a
script for example without the interactivity. you can do this by prepending `\` to the alias.

```zsh
function foo() {
    \rm path/to/file
}
```

## [Append/fix history file](http://superuser.com/questions/957913/how-to-fix-and-recover-a-corrupt-history-file-in-zsh)

```sh
$ mv .zsh_history .zsh_history_bad
$ strings .zsh_history_bad > .zsh_history
$ fc -R .zsh_history
```

## Get the last running command

```sh
$ fc -ln -1
```

## Check for a command

```zsh
if command -v <command> >/dev/null; then
 # Do something
fi
```
