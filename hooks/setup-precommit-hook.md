# How to set up pre-commit hook
You can set up a symlink using hooks/pre-commit as source file:

`$ cd .git/hooks/ && ln -s -f ../../hooks/pre-commit ./pre-commit`

so that every time you change the hook, change propragates to the
right directory where hooks are executed.
