---
name: update-github-info
description: Keep the GitHub Info page current with practical updates from GitHub sources.
on:
  schedule: daily
  workflow_dispatch:
permissions:
  contents: read
  pull-requests: read
engine: copilot
tools:
  edit:
  github:
    toolsets: [repos]
  web-fetch:
network:
  allowed:
    - github.blog
    - github.com
safe-outputs:
  create-pull-request:
    draft: true
    reviewers:
      - Mona
---

# Update GitHub Info

Read `notes/mona-notes.md` before making any changes.

Use web-fetch to read:

- https://github.blog/latest/
- https://github.blog/changelog/

Use the GitHub repository tools to read any repository guidance or reference files needed to understand the current content. Review `site/content/github-info.md`, then update that file with short, practical information that helps developers learn GitHub faster. Keep summaries concise and mention whether each update came from the GitHub Blog or GitHub Changelog.

Use the edit tool only to update `site/content/github-info.md`. When the update is complete, request the `create-pull-request` safe output with a clear title and summary so the changes are proposed in a pull request for Mona to review. Do not write directly to the default branch.