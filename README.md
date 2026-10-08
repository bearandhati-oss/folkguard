# Folkguard site (https://bearandhati-oss.github.io/folkguard)

Static site: home, support, privacy, and the invite landing page (/join). Served by GitHub Pages from the `bearandhati-oss/folkguard` repo, at https://bearandhati-oss.github.io/folkguard. Links are relative so they work under `/folkguard/`, and GitHub Pages serves `privacy.html` at `/privacy`.

The universal links file can't live here. Apple only reads `https://<domain>/.well-known/apple-app-site-association`, which on GitHub Pages is the account's root site, the `bearandhati-oss/bearandhati-oss.github.io` repo. That file is in `../site-root/`.

Publish both with `Scripts/publish-site.sh` (needs `gh auth login` as `bearandhati-oss`).

Check after deploying:
- https://bearandhati-oss.github.io/folkguard/privacy, /support, and /join load.
- `curl -sI https://bearandhati-oss.github.io/.well-known/apple-app-site-association` returns 200 with no redirect.
- `curl -s https://app-site-association.cdn-apple.com/a/v1/bearandhati-oss.github.io` shows the file (Apple's CDN, which is what iPhones actually read; it can lag up to a day).
