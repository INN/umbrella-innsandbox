# INN Sandbox

This repo exists as a venue whereby to use [WP Engine's `git push` workflow]() to deploy versions of [Largo](https://github.com/INN/largo) to https://innsandbox.wpengine.com/ 

## Updating Largo

It's a submodule.

1. Check out this repo.
2. `git submodule update --init --recursive`
3. `cd wp-content/themes/largo`
4. `git fetch; git checkout <branch>; git pull` where `<branch>` is the desired branch
5. `cd ..` to get you back into the umbrella repo
6. `git commit`
7. ` git push <target> <branch>` where `<branch>` is your branch and `<target>` is the name you gave the remote specified in [innsandbox's git push settings](https://my.wpengine.com/installs/innsandbox/git_push).

For ~reasons~ the git remote is:

```
git remote add development git@git.wpengine.com:production/innsandbox.git
```

## Local Setup instructions

See https://github.com/INN/docs/blob/master/projects/largo/umbrella-setup.md

