---
name: update-github-info
description: Draft practical GitHub Info updates for Mona using official GitHub sources and open a pull request for review.
on:
  workflow_dispatch:
  schedule:
    - cron: '17 9 * * *'
safe-outputs:
  create-pull-request:
    title-prefix: "[mona] "
    draft: true
    fallback-as-issue: false
tools:
  edit:
  web-fetch:
network:
  allowed:
    - github.blog
    - github.com
    - awesome-copilot.github.com
---

# Update Mona's GitHub Info website

Read `notes/mona-notes.md` before making changes.

Use these sources:
- `notes/mona-notes.md`
- GitHub Blog: https://github.blog/latest/
- GitHub Changelog: https://github.blog/changelog/
- Awesome Copilot workflows: https://awesome-copilot.github.com/workflows/

Use web-fetch to read https://awesome-copilot.github.com/workflows/ as an additional public source when it is relevant.

Update `site/content/github-info.md` with concise,
practical updates for readers and include source context when content comes
from the GitHub Blog, GitHub Changelog, or Awesome Copilot workflows.

Open a pull request for Mona to review.
Use a pull request title that mentions Mona or GitHub Info.
Do not write directly to `main`;
rely on `safe-outputs` with `create-pull-request`.

Follow these instructions carefully:

1. Read and review `notes/mona-notes.md` to understand Mona's voice and priorities.
2. Use web-fetch to read external public guidance, including the GitHub Blog latest page, the GitHub Changelog page, and https://awesome-copilot.github.com/workflows/ to identify recent, relevant updates.
3. Read repository guidance or reference files with GitHub repository API tools instead of terminal, CLI, or sandboxed commands when needed.
4. Summarize the most useful changes in a concise, practical way for readers of the GitHub Info site.
5. Update `site/content/github-info.md` with fresh, useful content grounded in the GitHub Blog, GitHub Changelog, and Awesome Copilot workflows when relevant.
6. Mention the source whenever material comes from the GitHub Blog, GitHub Changelog, or Awesome Copilot workflows.
7. Keep the changes short, clear, and developer-focused.
8. Open a pull request for Mona to review using `safe-outputs` and `create-pull-request`.
9. Do not write directly to `main`; use the pull request workflow so Mona can review it first.

The workflow should produce a concise update to the site and open a pull request for Mona to review. Include the GitHub Blog, GitHub Changelog, and Awesome Copilot workflows references in the resulting content where relevant, and ensure the final result is a clear GitHub Info update instead of a generic summary.

Use `safe-outputs` with `create-pull-request` to open the pull request and keep the change reviewable. The agent should update `site/content/github-info.md` and then open a pull request for Mona to review.
