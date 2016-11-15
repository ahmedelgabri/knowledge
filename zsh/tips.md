## Override an interactive alias

if you have `rm` to be aliased to `rm -i` _which you should anyway_ & you want to use `rm` in a script for example without the interactivity. you can do this by prepending `\` to the alias.

```zsh
function foo() {
    \rm path/to/file
}
```
