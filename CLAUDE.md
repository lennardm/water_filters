# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a MkDocs static documentation site for a guide on replacing a Kinetico water softener valve with a Clack WS1TT. The site is deployed to GitHub Pages automatically on push to `main`.

## Commands

Requires a Python virtual environment. The `.venv/` is already set up locally.

```bash
# Activate venv
source .venv/bin/activate

# Serve locally with live reload
mkdocs serve

# Build static site
mkdocs build

# Deploy to GitHub Pages (done automatically via CI, but can be run manually)
mkdocs gh-deploy --force
```

## Structure

- `docs/index.md` — the single page of content (the entire guide lives here)
- `mkdocs.yml` — site config (site name, nav)
- `.github/workflows/deploy.yml` — CI deploys to GitHub Pages on push to `main` using `mkdocs gh-deploy --force`
- `.venv/` — local Python venv (gitignored)
- `akvafors/` — gitignored local directory (likely scratch/reference material)

## Content Notes

The guide covers replacing a Kinetico 4060 M/T / 4060s OD MAC valve head with a Clack WS1TT CI. Content is technical and specific — edits should preserve accuracy of part numbers, flow rates, and configuration steps.
