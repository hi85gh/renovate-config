# @hi85/renovate-config

<a href="https://renovatebot.com">
  <img src="https://user-images.githubusercontent.com/33993836/73533974-595dec00-4463-11ea-8d56-441853970f73.png" alt="Renovate icon" width="80" align="right" />
</a>

[![npm version](https://img.shields.io/npm/v/@hi85/renovate-config)](https://www.npmjs.com/package/@hi85/renovate-config)
[![CircleCI status](https://img.shields.io/circleci/build/github/hi85gh/renovate-config.svg?label=test)](https://circleci.com/gh/hi85gh/renovate-config)
[![Renovate status](https://img.shields.io/badge/renovate-enabled-brightgreen.svg)](https://renovatebot.com/)
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
    "npm:unpublishSafe",
    ":label(renovate)",
    ":prHourlyLimitNone",
    ":rebaseStalePrs",
    ":timezone(Asia/Tokyo)"
  ],
  "npm": {
    "commitMessageTopic": "{{prettyDepType}} {{depName}}",
    "extends": [
      ":maintainLockFilesMonthly"
    ],
    "rangeStrategy": "bump"
  }
}
```

### `@hi85:automergeAllNonMajor`

Group and automerge all minor and patch updates.

<!-- prettier-ignore -->
```json
{
  "extends": [
    "group:allNonMajor",
    ":automergeMinor"
  ]
}
```

### `@hi85:scheduleWeekly`

Weekly schedule.

<!-- prettier-ignore -->
```json
{
  "schedule": [
    "after 6am on Monday",
    "before 9am on Monday"
  ]
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
