# GitHub Pages deployment

Repository `indigetal/uixpress-tutor-lms` must use Pages source **GitHub Actions**. The workflow on `main` reads committed artifacts and creates no commits.

Ledger: `approval.md`. A missing ledger, or one with no `instructor-admin.<hex>.css` names, publishes no CSS. Each name is copied only from `design-system/dist/`.

Default URL: `https://indigetal.github.io/uixpress-tutor-lms/instructor-admin.<content-hash>.css`.
