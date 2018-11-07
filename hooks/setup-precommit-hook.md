# Pre-commit hook
This pre-commit hook will be triggered for every `git commit` issued.

Source can be found [here](https://gist.github.com/wookietreiber/8e92f6db1bc632d501a9fa0bafbcb391)

It checks that diff files that contain the extension ".ya?ml" under
the folder `ansible/` are Lint compliant using `ansible-lint` tool.

You can find ansible-lint [here](https://github.com/ansible/ansible-lint).

## Setup pre-commit hook
If you want to use my custom pre-commit hook, you can set it up on
your environment by creating a symlink and making the script executable.

`$ ln -s -f ../../hooks/pre-commit .git/hooks/pre-commit`
`$ chmod +x hooks/pre-commit`

With this setup, you can modify the hook and commit the changes to git
without copying the file out of `.git/hook/` path.

## Requirements
 * ansible-lint
 * bash
