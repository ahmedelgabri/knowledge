# Profiling

## Find Slow Plugins During Actions:

```vim
:profile start profile.log
:profile func *
:profile file *
" At this point do slow actions
:profile pause
:noautocmd qall!
```

```
[n]vim --cmd 'profile start /tmp/profile.log' --cmd 'profile func *' --cmd 'profile file *'
```

## Startup time

> `--startuptime` is not
> [always accurate](https://github.com/neovim/neovim/issues/7348#issuecomment-333398166), prefer
> profile instead

Start vim with `--startuptime`, this command will output the startuptime data in `/tmp/vim/log` &
open the file too in the same time.

```sh
$ [n]vim --startuptime /tmp/vim.log /tmp/vim.log
```

The file will looks like this

```
times in msec
 clock   self+sourced   self:  sourced script
 clock   elapsed:              other lines

000.012  000.012: --- NVIM STARTING ---
000.815  000.803: locale set
001.676  000.862: inits 1
001.702  000.025: window checked
002.714  001.012: parsing arguments
002.718  000.005: expanding arguments
002.769  000.051: inits 2
002.966  000.196: init highlight
...
277.385  000.151  000.151: sourcing /Users/ahmed/.vim/plugged/vim-airline/autoload/airline/extensions/default.vim
302.302  000.328  000.328: sourcing /Users/ahmed/.vim/plugged/neomake/autoload/neomake/statusline.vim
...
364.173  003.731: first screen update
364.177  000.003: --- NVIM STARTED ---
```

What to look for is big time differences in the left side column between files & try to defer/lazy
load these plugins/files etc...

For more info check

```vim
:h --startuptime
```

also this was very useful for me to wrap my head around this
https://www.youtube.com/watch?v=wQ9uB8I0cCg
