# GREP & Regex

## GREP commands

Grep all files recursivly in current directory "."  that contain the string "md5" output in color:

```text
grep -r "md5" . --color 2>/dev/null
```

Grep all files recursivly in current directory "."  that **do NOT** the string "../include/isAuthenticated.php" output in color:

```text
grep -r "../include/isAuthenticated.php" . --color 2>/dev/null -L
```

Same as above but now only include files ending with **PHP**

```text
grep -r "../include/isAuthenticated.php" . --color 2>/dev/null -L --include \*.php
```



