# @hi85/renovate-config

<a href="https://renovatebot.com">
  <img src="https://user-images.githubusercontent.com/33993836/64076443-00492b00-cd00-11e9-88ea-c98919eab570.png" alt="Renovate icon" width="80" align="right" />
</a>

[![npm version](https://img.shields.io/npm/v/@hi85/renovate-config)](https://www.npmjs.com/package/@hi85/renovate-config)
[![CircleCI status](https://img.shields.io/circleci/build/github/hi85gh/renovate-config.svg?label=test)](https://circleci.com/gh/hi85gh/renovate-config)
[![Renovate status](https://badges.renovateapi.com/github/hi85gh/renovate-config)](https://renovatebot.com/)
![MIT License](https://img.shields.io/github/license/hi85gh/renovate-config)

My [shareable config](https://renovatebot.com/docs/config-presets/) for [Renovate](https://renovatebot.com).

## Setup

Enable Renovate in your repo and just `extends` in `renovate.json`.

```json
{
  "extends": ["@hi85"]
}
```

Note: You don't have to do `npm i -D @hi85/renovate-config`.

## Presets

### `@hi85`

Default preset.

<!-- prettier-ignore -->
```json
{
  "extends": [
    "config:base",
    ":label(renovate)",
    ":prHourlyLimitNone",
    ":rebaseStalePrs",
    ":timezone(Asia/Tokyo)"
  ],
  "npm": {
    "commitMessageTopic": "{{prettyDepType}} {{depName}}",
    "extends": [
      ":maintainLockFilesMonthly",
      ":unpublishSafe"
    ],
    "prBodyColumns": [
      "Package",
      "Update",
      "Type",
      "Change",
      "CompatibilityScore"
    ],
    "prBodyDefinitions": {
      "CompatibilityScore": "[![compatibility-score for {{{depNameEscaped}}}](https://api.dependabot.com/badges/compatibility_score?dependency-name={{{depNameEscaped}}}&package-manager=npm_and_yarn&previous-version={{{fromVersion}}}&new-version={{{toVersion}}})](https://dependabot.com/compatibility-score/?dependency-name={{{depNameEscaped}}}&package-manager=npm_and_yarn&previous-version={{{fromVersion}}}&new-version={{{toVersion}}})"
    },
    "rangeStrategy": "bump"
  }
}
```

### `@hi85:semanticCommitTypeAllChore`

Set the semantic commit type for all dependencies to `chore`.

<!-- prettier-ignore -->
```json
{
  "extends": [
    ":semanticCommitTypeAll(chore)",
    ":semanticCommits"
  ]
}
```

## References

- [Renovate Docs](https://renovatebot.com/docs/)
- [Configuration Options \| Renovate Docs](https://renovatebot.com/docs/configuration-options/)
- [Default Presets \| Renovate Docs](https://renovatebot.com/docs/presets-default/)

## License

[MIT License](https://opensource.org/licenses/MIT)
