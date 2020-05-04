# @prescott/commitlint-preset

A common [commitlint](https://github.com/conventional-changelog/commitlint) preset for personal TypeScript projects.

## IMPORTANT NnOTE

This preset requires global installation of `commitizen`. Make sure `commitizen` is installed globally: 

```bash
$ npm install commitizen -g
```

## Local Setup

If you want to lint commit message via Git hook to enforce commit message style in local dev environment, 
Follow these instructions.

In this setup, You have to install additional [`husky`](https://github.com/typicode/husky) dependency. 

```bash
$ npm install @prescott/commitlint-preset husky --save-dev
```

Add the following to `package.json`

```json
{
  "config": {
    "commitizen": {
      "path": "cz-conventional-changelog"
    }
  },
  "husky": {
    "hooks": {
      "commit-msg": "commitlint -E HUSKY_GIT_PARAMS"
    }
  },
  "commitlint": {
    "extends": [
      "@prescott/commitlint-preset"
    ]
  }
}
```

Done. There is no any additional steps to check commit message. 
commitlint will be automatically executed every commits.


## CI Setup

If you want to lint commit message via CI environment, Follow these instructions.

In this setup, `husky` is not required.

Add the following to `package.json`

```json
{
  "config": {
    "commitizen": {
      "path": "cz-conventional-changelog"
    }
  },
  "commitlint": {
    "extends": [
      "@prescott/commitlint-preset"
    ]
  }
}
```

Done. 
Please follow below steps to execute commitlint.

#### Github Actions

Add following to workflow.yml

```yaml
  steps:
    - name: CommitLint
      run: npx commitlint --from ${{ github.event.before || github.event.head || 'master' }} --verbose
```

#### Travis CI

Install additional dependency:

```bash
$ npm install @commitlint/travis-cli --save-dev
```

Add following to travis.yml

```yaml
# travis.yml
language: node_js
script:
  - commitlint-travis
```

#### Other CI Environments

Execute following to check commit message:

```bash
$ npx run commitlint --from [COMMIT_SHA1] --to [COMMIT_SHA1]
```


## Commit Helpers

![cz-cli](https://github.com/commitizen/cz-cli/raw/master/meta/screenshots/add-commit.png)

[`cz-cli`](https://github.com/commitizen/cz-cli) provides git extension to create semantic commits.

Simply use `git cz` instead of using `git commit`.  
