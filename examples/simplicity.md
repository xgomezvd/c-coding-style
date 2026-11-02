# Simplicity

Prefer straightforward implementations. Avoid unnecessary operations,
conditions, variables, and abstractions.

## Unnecessary NULL checks

- `free()` accepts NULL pointers, so checking the pointer beforehand is
  unnecessary. So, avoid defensive checks when the operation is already
  guaranteed to handle the condition safely by the C standard.

Avoid:

```c
if (ptr != NULL) {
    free(ptr);
}
```

Prefer:

```c
free(ptr);
```