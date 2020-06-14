# How to Add Gatekeeper Exceptions from Command Line in Mac OS X

```
spctl --add /path/to/your.app
```

or

```
find /path/to/your.app -exec xattr -c {}
```
