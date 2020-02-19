# repro-eslint-dotfiles-not-working

This reproduction repo shows how eslint will ignore dotfiles when they are declard in `overrides` section in the [ESLint config](.eslintrc.js).

You can try the below commadns after having installed dependencies with `yarn`

**Test 1 - Expected error is thrown** with `yarn run eslint my-file.js`

```
$ yarn run eslint my-file.js 
yarn run v1.21.1
$ /home/ayzing/workspace/repro-eslint-dotfiles-not-working/node_modules/.bin/eslint my-file.js

/home/ayzing/workspace/repro-eslint-dotfiles-not-working/my-file.js
  1:7  error  'foo' is assigned a value but never used  no-unused-vars

✖ 1 problem (1 error, 0 warnings)
```

**Test 2 - No error thrown with dotfile** with `yarn run eslint .my-dotfile.js`

```
$ yarn run eslint .my-dotfile.js 
yarn run v1.21.1
$ /home/ayzing/workspace/repro-eslint-dotfiles-not-working/node_modules/.bin/eslint .my-dotfile.js

/home/ayzing/workspace/repro-eslint-dotfiles-not-working/.my-dotfile.js
  0:0  warning  File ignored by default.  Use a negated ignore pattern (like "--ignore-pattern '!<relative/path/to/filename>'") to override

✖ 1 problem (0 errors, 1 warning)
```