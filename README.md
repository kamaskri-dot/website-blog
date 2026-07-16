# website-blog

Source of truth for the **blog section only** of https://cdmcg.com.au

## How this publishes

A cron job on the cPanel host runs `pull_blog.sh` every 15 minutes. It downloads this
repo as a zip over the public GitHub API (no credentials — this repo is public), and
syncs **only the `blog/` directory** into `public_html/blog/`.

## Rules

- Only `blog/` is deployed. Nothing else in this repo touches the live site.
- Everything committed here is **published to the public web**. Never commit drafts,
  credentials, or anything not approved for publication.
- Commit an article on its **publication date**, not before. This repo is public, so
  content is visible here the moment it is pushed.
- The sync **adds and overwrites, it never deletes**. Removing a file here does NOT
  remove it from the live site. That must be done manually in cPanel.