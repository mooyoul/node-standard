# @prescott/renovate-config

A common [Renovate](https://github.com/renovatebot/renovate) configuration for personal projects.

## Setup

```bash
$ npm install @prescott/renovate-config --save-dev
```

Add the following to `renovate.json`

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
