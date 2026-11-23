# jahlilshannon.netlify.app

Personal portfolio. One self-contained HTML file plus an `assets/` folder (photo, resume PDF, preview images). No build step, no dependencies.

## Editing

`main` is protected: every change goes through a pull request, and two checks must pass before it can merge.

```
git switch -c <short-description>
# edit index.html
git commit -am "Update <what changed>"
git push -u origin <short-description>
gh pr create --fill
```

Then open the Netlify deploy preview linked on the PR, check it on a phone and a laptop, and merge. Netlify deploys `main` automatically.

When you change the page, update the "Last updated" line in the footer.

## Checks

- **guardrails**: fails if a page contains an em-dash, a phone number, retired delivery counts, or expired certifications. Rules live in `.github/banned-patterns.txt`.
- **links**: fails on broken local links, images or files.

## Why one file

Nothing here needs a framework. A single file means the site can be edited from
any machine with a text editor, survives without a toolchain, and still renders
in three years. The cost is that `index.html` grows; split it when it stops being
readable, not before.

## Deploy

Netlify, publishing from the repository root. `netlify.toml` declares the publish
directory and the security headers, so the configuration lives in version control
rather than in a dashboard.
