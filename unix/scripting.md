# Shell scripting

## When using double `[[]]` square brackets no need to quote a variable

These are fine

```bash
if [[ -d $DIR ]]; then
    # do something
fi

# or

if [[ -d "$DIR/folder" ]]; then
    # do something
fi
```

This doesn't work as expected


```bash
if [[ -d "$DIR" ]]; then
    # do something
fi
```

but this one does


```bash
if [-d "$DIR" ]; then
    # do something
fi
```

---

## Arrays

```sh
MY_ARRAY=(one two three)
# or
MY_ARRAY=(
one
two
three
)

echo ${MY_ARRAY[@]} # Will echo out the whole array
echo ${#MY_ARRAY[@]} # Will echo out the length of the array
```
