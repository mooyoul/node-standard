# @prescott/semantic-release-config

A common [semantic-release](https://github.com/semantic-release/semantic-release) configuration for personal TypeScript projects.

## Setup

```bash
$ npm install @prescott/semantic-release-config --save-dev
```

Add the following to `.releaserc.json`

```json
{
  "extends": "@prescott/semantic-release-config"
}
```

Add the following to CI Script:

```bash
$ npx semantic-release
```


## Configurations

#### Default

This is commonly used preset.

```json
{
  "extends": "@prescott/semantic-release-config"
}
```


#### Monorepo/Embedded Packages

This is a special configuration for monorepo packages, or embedded packages where package is co-located inside service repository.

For example, Media SDK is located in Media Service repository, and non-sdk related commits are not using semantic-commits.

In this case, Follow below setup steps.

First, Add `semantic-release-commit-filter` package to `devDependencies`:

```bash
$ npm i semantic-release-commit-filter --save-dev --save-exact
```
 
Then, Use following semantic-release configuration:

```json
{
  "extends": ["semantic-release-commit-filter", "@vingle/semantic-release-config"],
  "tagFormat": "[PACKAGE_NAME]-v${version}"
}
```

That's all! Run `semantic-release` inside package directory:

For example:

```bash
$ cd media-sdk
$ npx semantic-release
```

You can also check your configuration before automated release:

```bash
$ npx semantic-release --dry-run
``` 
