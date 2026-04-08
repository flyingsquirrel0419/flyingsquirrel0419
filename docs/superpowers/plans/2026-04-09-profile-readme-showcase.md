# GitHub Profile Showcase Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Rebuild the profile README and add GitHub Actions that automatically generate showcase visuals.

**Architecture:** Keep the profile repository lightweight. Store authored content in `README.md`, generate `github-metrics.svg` in-place through a workflow, and publish snake assets to an `output` branch for raw embedding.

**Tech Stack:** Markdown, GitHub Actions, lowlighter/metrics, Platane/snk

---

### Task 1: Replace the profile README

**Files:**
- Modify: `README.md`

- [ ] **Step 1: Replace the existing README content**

Use a project-first structure with these sections:

```md
Hero banner
Typing headline
Social badges
Featured Project
Profile Snapshot
What I Work On
Tech Stack
Metrics and Activity
Contact
Footer banner
```

- [ ] **Step 2: Verify the README structure**

Run: `sed -n '1,260p' README.md`
Expected: all target sections appear in the intended order and `Iodine` appears before the profile snapshot section.

### Task 2: Add the metrics workflow

**Files:**
- Create: `.github/workflows/metrics.yml`

- [ ] **Step 1: Add a scheduled metrics workflow**

Use `lowlighter/metrics` with:

```yaml
permissions:
  contents: write
```

and configure:

```yaml
token: ${{ secrets.METRICS_TOKEN }}
user: flyingsquirrel0419
filename: github-metrics.svg
config_timezone: Asia/Seoul
```

- [ ] **Step 2: Verify the workflow file**

Run: `sed -n '1,220p' .github/workflows/metrics.yml`
Expected: workflow includes `schedule`, `workflow_dispatch`, `push`, and writes `github-metrics.svg`.

### Task 3: Add the contribution snake workflow

**Files:**
- Create: `.github/workflows/snake.yml`

- [ ] **Step 1: Add a scheduled snake workflow**

Use `Platane/snk@v3` to generate:

```text
dist/github-contribution-grid-snake.svg
dist/github-contribution-grid-snake-dark.svg
```

Then publish the `dist` directory to the `output` branch.

- [ ] **Step 2: Verify the workflow file**

Run: `sed -n '1,220p' .github/workflows/snake.yml`
Expected: workflow publishes generated files with `GITHUB_TOKEN`.

### Task 4: Record design and setup notes

**Files:**
- Create: `docs/superpowers/specs/2026-04-09-profile-readme-design.md`
- Create: `docs/superpowers/plans/2026-04-09-profile-readme-showcase.md`

- [ ] **Step 1: Save the chosen design decisions**

Document the profile direction, automation design, and known risks.

- [ ] **Step 2: Verify the documentation files**

Run: `find docs/superpowers -maxdepth 3 -type f | sort`
Expected: both the design spec and implementation plan files exist.
