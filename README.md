# jahlilshannon.com

Personal portfolio. One self-contained HTML file, no build step, no dependencies.

## Editing

Edit `index.html`, commit, push. Netlify deploys from `main` automatically.

```
git add index.html
git commit -m "Update <what changed>"
git push
```

## Why one file

Nothing here needs a framework. A single file means the site can be edited from
any machine with a text editor, survives without a toolchain, and still renders
in three years. The cost is that `index.html` grows; split it when it stops being
readable, not before.

## Deploy

Netlify, publishing from the repository root. `netlify.toml` declares the publish
directory and the security headers, so the configuration lives in version control
rather than in a dashboard.
