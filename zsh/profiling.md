## Check startup time for any shell

```sh
for i ($(seq 1 10)) /usr/bin/time zsh -i -l -c exit
```
