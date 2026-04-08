# GitHub Profile Setup

## Required Secret

Create a repository secret named `METRICS_TOKEN`.

Suggested token access:

- `read:user`
- `read:org`
- `public_repo`

If you want private contribution data included in metrics, use a token with the broader repository read scope that matches your account settings.

## Required Repository Setting

For the snake workflow, make sure the repository allows workflow write access:

1. Open `Settings`
2. Open `Actions` → `General`
3. Under `Workflow permissions`, select `Read and write permissions`
4. Save the change

## First Run

1. Add the `METRICS_TOKEN` secret
2. Open the `Actions` tab
3. Run `Generate Metrics`
4. Run `Generate Snake`
5. Confirm that:
   - `github-metrics.svg` is updated on the default branch
   - the `output` branch is created
   - `github-contribution-grid-snake-dark.svg` is available from the `output` branch
