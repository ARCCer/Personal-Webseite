# Deployment

This Quarto website is deployed with GitHub Pages through GitHub Actions.

Target public URL:

```text
https://chuanzhu.site/
```

## Strategy

The `main` branch stores the source files only:

- Quarto source files such as `index.qmd`, `research.qmd`, `industry.qmd`, `teaching-service.qmd`, and `cv.qmd`
- Site configuration in `_quarto.yml`
- Styling in `styles.css`
- Static assets such as the portrait image, CV PDF, paper PDFs, and `robots.txt`
- The GitHub Actions workflow in `.github/workflows/publish.yml`

The rendered `_site/` folder is not committed manually. It is generated during the GitHub Actions run and uploaded as a GitHub Pages artifact.

## Trigger Branch

Deployment runs when changes are pushed to:

```text
main
```

The workflow can also be started manually from the GitHub Actions tab because it includes `workflow_dispatch`.

## Build Command

The workflow builds the site with:

```bash
quarto render
```

The current `_quarto.yml` is configured to render the public website pages only.

## Deployed Folder

The rendered output folder is:

```text
_site
```

GitHub Actions uploads `_site/` with `actions/upload-pages-artifact` and deploys it with `actions/deploy-pages`.

## Manual GitHub Pages Setting

In the GitHub repository, keep GitHub Pages deployment from Actions enabled:

1. Open the repository on GitHub.
2. Go to `Settings`.
3. Go to `Pages`.
4. Under `Build and deployment`, set `Source` to `GitHub Actions`.
5. Under `Custom domain`, set `chuanzhu.site`.
6. Enable `Enforce HTTPS` after GitHub finishes checking the domain.

After this setting is enabled, every push to `main` should build and publish the site automatically.

The DNS records for the custom domain should point to GitHub Pages. The current public site is expected to resolve at:

```text
https://chuanzhu.site/
```

No rendered `_site/` folder should be committed manually.

## Local Preview Before Release

Before pushing to GitHub, run:

```bash
quarto render
```

Then preview the local pages:

- Home: `http://localhost:4321/`
- Research: `http://localhost:4321/research.html`
- Industry: `http://localhost:4321/industry.html`
- Teaching & Service: `http://localhost:4321/teaching-service.html`
- CV: `http://localhost:4321/cv.html`

Do not commit `_site/`. The folder is ignored locally and rebuilt by GitHub Actions during deployment.
