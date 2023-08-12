# renovate-config-oss

A shareable renovate config for my OSS projects. I have a self-hosted Renovate Bot on Github Apps.

## How to enable Renovate for my OSS projects

- Install the secrets to a repository

  ```
  git clone <your-repo>
  cd <your-repo>

  # RENOVATE_APP_ID
  gh secret set RENOVATE_APP_ID --app actions --body "$(jq -r .app_id renovate-for-tknetworks.json)"

  # RENOVATE_APP_INST_ID
  gh secret set RENOVATE_APP_INST_ID --app actions --body "$(jq -r .inst_id renovate-for-tknetworks.json)"

  # RENOVATE_APP_PRIV_KEY
  gh secret set RENOVATE_APP_PRIV_KEY --app actions < renovate-for-tknetworks.2023-08-05.private-key.pem
  ```

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
