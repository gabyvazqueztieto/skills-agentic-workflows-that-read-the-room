---
name: update-github-info
on:
  schedule: daily
  workflow_dispatch:

permissions:
  contents: read

tools:
  edit:
  web-fetch:

network:
  allowed:
    - github.blog
    - github.com

safe-outputs:
  create-pull-request:
    base-branch: main
    draft: true
---

# Update GitHub Info

Refresh Mona's GitHub Info content using recent, useful updates from the official GitHub Blog and Changelog.

## Instructions

1. Read `notes/mona-notes.md` and the current `site/content/github-info.md` before making changes.
2. Use `web-fetch` to read both `https://github.blog/latest/` and `https://github.blog/changelog/`. Follow links on those pages only as needed to verify relevant details, and use only official GitHub sources.
3. Select recent updates that provide practical value to developers. Keep summaries short, factual, and consistent with Mona's editorial notes. Do not invent details or copy long passages.
4. Update `site/content/github-info.md`, preserving its existing structure and useful material. Cite the direct GitHub Blog or Changelog source for every new or changed update.
5. Review the diff to ensure it only changes the intended content and that source links support the claims.
6. Propose the changes as a pull request for Mona to review. Include a concise summary and the sources used in the pull request description. Do not write directly to `main` or merge the pull request.