# GitHub Profile README Design

## Goal

Rebuild the profile README for `flyingsquirrel0419` into a project-first portfolio showcase inspired by metrics-based profile repositories, but visually distinct from the reference.

## Constraints

- Keep the result English-first
- Make the featured project appear before the self-introduction section
- Use GitHub Actions for automated showcase assets
- Avoid a near-clone of the referenced profile repository
- Stay within a simple profile-repo structure with minimal maintenance burden

## Chosen Direction

Use a portfolio-first hybrid layout:

- Hero banner and animated positioning statement at the top
- Featured project section for `Iodine`
- Brief profile snapshot and work-focus section
- Tech stack section with badges
- Metrics and activity showcase using generated and hosted SVG assets
- Contact section and footer

## Automation Design

- `metrics.yml` generates `github-metrics.svg` with `lowlighter/metrics`
- `snake.yml` generates contribution snake assets and publishes them to the `output` branch
- Stats, streak, and activity graph remain externally embedded because they are already standard, low-maintenance profile widgets

## Content Strategy

- Emphasize practical building and operating real-world projects
- Present `Iodine` as the anchor project
- Keep text short, clear, and portfolio-oriented
- Use visuals to make the lower half of the profile feel active and maintained

## Risks

- `github-metrics.svg` will not populate until `METRICS_TOKEN` is configured
- Snake assets will not appear until the workflow runs and the `output` branch is created
- Pinned-card visualization may feel slightly meta because it points to the profile repository rather than the bot repository
