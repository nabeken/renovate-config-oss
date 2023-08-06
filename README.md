# renovate-config-oss

A shareable renovate config for my OSS projects. I have a self-hosted Renovate Bot on Github Apps.

## How to invite my Renovate Github Apps

TBD

## How to use

Refer to this config in `extends` like below:
```json
{
  "extends": [
    "github>nabeken/renovate-config-oss"
  ]
}
```

## Available presets

**groupGoVersionUpgrade**: Upgrade Go runtime version in Github Actions and group it together in a single PR:
```json
{
  "extends": [
    "github>nabeken/renovate-config-oss:groupGoVersionUpgrade"
  ]
}
```

In the Github Action, you can write it like below:
```
env:
  # renovate: datasource=golang-version depName=golang
  GO_VERSION: '1.20.6'
```

**groupGithubActions**: Group Github Actions upgrade in a single PR (minor/major):
```json
{
  "extends": [
    "github>nabeken/renovate-config-oss:groupGithubActions"
  ]
}
```

## References

- https://github.com/hatena/renovate-config
- https://github.com/funteractive-inc/renovate-config
