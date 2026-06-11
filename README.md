# Stephen Rowley — Klaviyo Specialist site

The marketing site for Stephen Rowley, a Klaviyo / retention-marketing
consultant. It's a single landing page built as a lead-generation funnel for a
free Klaviyo audit.

**Live at:** https://steverowley.github.io/stephen-rowley-site/

## What's in the repo

| File         | What it does                                                                 |
| ------------ | --------------------------------------------------------------------------- |
| `index.html` | The entire site — HTML, CSS, and JavaScript are all inlined in this one file. |
| `llms.txt`   | A plain-text summary of the services and credentials, written for AI search engines and chatbots to read. |
| `README.md`  | This file.                                                                  |

There's no build step and no dependencies. The page is plain HTML, so you can
open `index.html` directly in a browser to preview it.

## Hosting (GitHub Pages)

The site is served by **GitHub Pages** straight from this repository — no build
pipeline, no separate host, no monthly cost. Pages is already enabled and the
site is live at https://steverowley.github.io/stephen-rowley-site/.

Every change merged into `main` republishes automatically within a minute or
two. The current setup (repo → **Settings** → **Pages**) is **Deploy from a
branch**, branch **`main`**, folder **`/ (root)`** — adjust it there if you ever
move the source.

## The Klaviyo integration

Two pieces, both in `index.html` and both using the public site ID `UaaaRc`
(safe to expose — it can only subscribe people, never read account data):

- **The audit-request form** (the "Request my free audit" form) submits straight
  to Klaviyo's client subscribe API and adds the lead to list `WNEmWF`, with
  their store URL and biggest email frustration saved as profile properties.
- **Onsite tracking** (`klaviyo.js`, loaded in the `<head>`) records "Active on
  Site" activity. When someone submits the form, the page identifies their
  browser to Klaviyo, so their return visits show up on their profile.

## Making changes

Because everything lives in `index.html`, editing the site means editing that one
file. Work on a branch, open a pull request, and once it's merged into `main`
GitHub Pages redeploys on its own.
