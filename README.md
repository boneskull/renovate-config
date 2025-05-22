# renovate-config

> boneskull's [inherited Renovate configuration](https://docs.renovatebot.com/mend-hosted/hosted-apps-config/#inherited-config)

## Settings

```json5
extends: [
  // send PRs to resolve dependabot alerts
  // https://docs.renovatebot.com/configuration-options/#vulnerabilityalerts
  ':enableVulnerabilityAlerts',

  // commit messages in conventional commits format
  // https://docs.renovatebot.com/presets-default/#semanticcommits
  ':semanticCommits',

  // group all eslint-related & prettier updates
  // https://docs.renovatebot.com/presets-group/#grouplinters
  'group:linters',

  // group all @types/* updates
  // https://docs.renovatebot.com/presets-group/#groupdefinitelytyped
  'group:definitelyTyped',

  // only update after packages can no longer be unpublished
  // https://docs.renovatebot.com/presets-npm/#npmunpublishsafe
  'npm:unpublishSafe',

  // pin github action digests
  // https://docs.renovatebot.com/presets-helpers/#helperspingithubactiondigests
  'helpers:pinGitHubActionDigests',

  // self-update config file when needed
  // https://docs.renovatebot.com/configuration-options/#configmigration
  ':configMigration',

  // https://docs.renovatebot.com/presets-default/#automergedigest
  ':automergeDigest',

  // https://docs.renovatebot.com/presets-default/#automergeminor
  ':automergeMinor',
],
labels: ['dependencies'],
ignorePaths: [
  '**/node_modules/**',
  '**/test/**',
  '**/demo/**',
  '**/example*/**',
],
```

## Usage

Create `.github/renovate.json5` in the repo and add:

```json5
{
  $schema: "https://docs.renovatebot.com/renovate-schema.json",
  extends: [
    "config:js-lib", // or 'config:js-app'
  ],
}
```

The inherited config should automatically be applied to all repos owned by `boneskull`.

## Notes

It is apparently [not possible](https://github.com/renovatebot/renovate/pull/27864) to use a `.json5` configuration file in the inherited config when using Mend-hosted Renovate ([discussion](https://github.com/renovatebot/renovate/discussions/36096)).

## License

This is free and unencumbered software released into the public domain.
