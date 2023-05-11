The `less` command

Option 1: `less -f`

This option forces less to open the file even if it is a directory. While using less without this option leads to an error, using the option tries to open it and then open the directory.

For example, without -f, we get the following output:

```
dhyan@MacBook-Pro-6 technical % less biomed
biomed is a directory
```