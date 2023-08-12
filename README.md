# renovate-config-oss

A shareable renovate config and self-hosted Renovate Github Apps runner for my OSS projects.

## How to enable Renovate for my OSS projects

- Add a new repository to the self-hosted Renovate Github Apps repository acccess
- Setup `.github/renovate.json` in a repository
- Add a repository to `.github/renovate-global.json`

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

**recommended**: A recommended preset for my OSS projects:
```json
{
  "extends": [
    "github>nabeken/renovate-config-oss:recommended"
  ]
}
```

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

**githubLocalActionsDefaultVersions**: Update the default version in `action.yml`
```json
{
  "extends": [
    "github>nabeken/renovate-config-oss:githubLocalActionsDefaultVersions"
  ]
}
```

## References

- https://github.com/hatena/renovate-config
- https://github.com/funteractive-inc/renovate-config
