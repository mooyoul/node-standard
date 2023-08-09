# @prescott/renovate-config

A common [Renovate](https://github.com/renovatebot/renovate) configuration for personal projects.

## Setup

Add the following to `renovate.json`

```json
{
  "extends": ["github>mooyoul/node-standard//renovate-config/default"]
}
```

## GitHub Hosted Presets

### Node.js specific presets

#### Node.js 18

```json
{
  "extends": [
    "github>mooyoul/node-standard//renovate-config/default",
    "github>mooyoul/node-standard//renovate-config/nodejs18"
  ]
}
```


### AWS Lambda specific presets

For AWS Lambda projects, Use following renovate preset:

```json
{
  "extends": [
    "github>mooyoul/node-standard//renovate-config/default",
    "github>mooyoul/node-standard//renovate-config/nodejs18",
    "github>mooyoul/node-standard//renovate-config/lambda"
  ]
}
```
### Semantic Commit specific presets

For semantic-release dependent projects, Use following renovate preset:

```json
{
  "extends": [
    "github>mooyoul/node-standard//renovate-config/default",
    "github>mooyoul/node-standard//renovate-config/semantic-commit"
  ]
}
```


## Deprecated NPM Hosted Presets

> [!WARNING]
> NPM Hosted Presets are obsolete and new presets are hosted on GitHub.
> There won't be any updates on NPM Hosted Presets (e.g. presets for newer Node.js versions)

### Default

```json
{
  "extends": ["@prescott"]
}
```

### Node.js specific presets

#### Node.js 8

```json
{
  "extends": ["@prescott", "@prescott:nodejs8"]
}
```

#### Node.js 10

```json
{
  "extends": ["@prescott", "@prescott:nodejs10"]
}
```
#### Node.js 12

```json
{
  "extends": ["@prescott", "@prescott:nodejs12"]
}
```


### AWS Lambda specific presets

For AWS Lambda projects, Use following renovate preset:

```json
{
  "extends": ["@prescott", "@prescott:nodejs12", "@prescott:lambda"]
}
```

### Semantic Commit specific presets

For semantic-release dependent projects, Use following renovate preset:

```json
{
  "extends": ["@prescott", "@prescott:semantic-commit"]
}
```
