<!-- markdownlint-disable -->

# Hardening Report: backstage--actions--yarn-install/v0.6.17

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **backstage--actions--yarn-install/v0.6.17** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

The action uses `actions/cache@v4` in two steps, referencing a mutable tag (`@v4`) instead of a pinned full 40-character SHA commit hash. This means the action could silently pull in a different (potentially malicious) version of the dependency if the tag is moved. Both occurrences should be replaced with a full SHA digest, e.g. `actions/cache@<40-char-sha> # v4`.

Locations:

- `action.yml:20`
- `action.yml:30`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Replaced both occurrences of `actions/cache@v4` in hardened/action/action.yml with the pinned SHA `actions/cache@0057852bfaa89a56745cba8c7296529d2fc39830 # v4`. The SHA was resolved via lookup_action_sha. No other findings were present.

