# again.sh
Repeat from command history with token replacement, etc.


## Idea

* https://www.gnu.org/software/bash/manual/bashref.html#History-Interaction

```sh
bower search magnificent
again -2 info
# excutes `bower info magnificent` with 2nd token replaced
```

```sh
# custom delimiter, like `cut`
again -d\t -2 foo
```

```sh
# multiple tokens
again -2 foo -4 bar
```

```sh
# `history` reference, like `!`
again -h-2 -3 foo
again -h10004 -3 foo
```


### Implementation

```
history | tail -n1 | cut -d' ' -f3-
```
