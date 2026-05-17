# Repository Instructions

This repository is my personal academic website.

## Project Rules

1. Preserve the existing framework unless I explicitly approve a migration.
2. Preserve existing deployment configuration unless I explicitly ask to change it.
3. Do not add new production dependencies unless clearly necessary.
4. Do not invent academic information, publications, awards, affiliations, grants, talks, or links.
5. When uncertain about personal or academic content, leave a clear TODO instead of fabricating details.
6. Use a professional academic tone.
7. Keep the website clean, concise, research-oriented, and easy to maintain.
8. Prioritize mobile responsiveness, accessibility, SEO, and readable typography.
9. Use my provided content as the source of truth.
10. Run available build, lint, or test commands after code changes.
11. Summarize all modified files after each task.
12. Prefer small, reviewable changes over large uncontrolled rewrites.

## Review Guidelines

- Flag broken links as high-priority.
- Flag invented academic facts as high-priority.
- Flag deployment-breaking changes as high-priority.
- Flag accessibility and mobile responsiveness problems.
- Flag overcomplicated design or unnecessary dependencies.

## Quarto Deployment Rules

1. This is a Quarto website.
2. Always run `quarto render` after modifying website files.
3. Do not commit the rendered `_site/` folder unless explicitly instructed.
4. Keep GitHub Pages deployment through GitHub Actions.
5. Do not change deployment configuration unless explicitly requested.
6. Use relative paths for internal links and static assets.
7. Do not invent academic content.
8. Summarize render results after each website change.
