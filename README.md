# Dev Ops Dev

A free, offline-ready **DevOps study app** (Progressive Web App). Learn by reading, watching animated walkthroughs, running commands in a simulated terminal and playing with interactive labs.

**Live demo:** `https://soorajacontec.github.io/devopsdev/` (after enabling GitHub Pages, see below)

## Features

- **11 lessons**: Linux, Networking, Git, Docker, Kubernetes, CI/CD, Terraform, Ansible, Monitoring, Cloud, DevSecOps
- **580+ key concepts**: click any card for a detailed explanation, a code example and a live mini-terminal
- **150+ copy-ready commands** with a searchable command library
- **21 interactive labs**: pipeline simulator, Kubernetes cluster, Git branching, Docker lifecycle, chmod, cron, Terraform plan/apply, SLO calculator, CIDR calculator, DNS resolution, TCP handshake, firewall tester, load balancer, shell pipeline builder, process & signals, systemd, regex tester, filesystem explorer and quizzes
- **Sandbox terminal**: a safe, simulated shell (git, docker, kubectl, terraform, ansible, aws, ip, dig, ping …)
- **15 study themes** with ambient animations and generated ambient sound
- **9 generated music tracks** (Jingle Bells, Lo-fi, Zen, Jazz, Chiptune …), all synthesised in the browser
- **Installable & offline**: service worker caches the app shell
- Progress tracking saved in your browser (`localStorage`)

## Tech

Plain HTML, CSS and vanilla JavaScript in a single `index.html`. No build step, no dependencies, no tracking. Audio is generated with the Web Audio API, so there are no media files.

## Run locally

Any static server works:

```bash
python3 -m http.server 8080
# open http://localhost:8080
```

> The service worker needs `http://localhost` or HTTPS (not `file://`).

## Deploy to GitHub Pages

1. Create a new GitHub repository and push this folder (commands below).
2. In the repo go to **Settings → Pages → Build and deployment → Source: GitHub Actions**.
3. The included workflow (`.github/workflows/pages.yml`) publishes the site on every push to `main`.

All asset paths are relative, so it works under `https://soorajacontec.github.io/devopsdev/`.

```bash
git init -b main
git add .
git commit -m "Initial commit: Dev Ops Dev PWA"
git remote add origin git@github.com:soorajacontec/devopsdev.git
git push -u origin main
```

## Updating the app

When you change `index.html`, bump the cache name in `sw.js` (`const CACHE = 'devopsdev-vNN'`) so installed users receive the new version.

## Project structure

```
index.html            app (HTML + CSS + JS)
sw.js                 service worker (offline cache)
manifest.json         PWA manifest
icon-*.png            app icons
apple-touch-icon.png  iOS icon
.github/workflows/    GitHub Pages deployment
```

## Contributing

Issues and pull requests are welcome. Content lives in the `LESSONS`, `DETAIL` and lab sections of `index.html`.

## Credits

Created by **SSK-BLUM**.

## Licence

[MIT](LICENSE)
