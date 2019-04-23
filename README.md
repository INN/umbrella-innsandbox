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

<details>
<summary>
those reasons
</summary>

From a chat:

This site was created before WPE moved from "Legacy Staging" sites to their current (early 2019) three-env production/staging/development setup. 

In git remote URLs like `git@git.wpengine.com:production/innsandbox.git`, the "production" there reflects the legacy production site of an environment, and for legacy staging sites the "production" is replaced with "staging".

After WPE switched, now all site installs are found under "production", so even for a site that's a development environment, you'll see this:

```

$ ssh git@git.wpengine.com info
hello example-user
 R W	production/innsandbox
 R W	staging/innsandbox
```

The full chat transcript: 

> The production environment has a legacy staging site. [In git,] [the production environment] is production & legacy staging site known as Staging.  Now all environments in user portal (production, staging, dev) are considered "production".  Each of those environments has it's own legacy staging environment from wp-admin> wpeingine> legacy staging.  The legacy staging for each environment is known as the STAGING and everything in user portal (prod, staging, dev) is now known as PRODUCTION

</details>

## Local Setup instructions

See https://github.com/INN/docs/blob/master/projects/largo/umbrella-setup.md

