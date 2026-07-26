# gh-workflow-cost

> Find out which matrix leg is quietly eating the Actions budget.

**Status:** 🚧 In development

## Overview

Estimate GitHub Actions minutes and cost per workflow and per job from run history, showing which matrix leg is actually expensive.

## Features

- Pulls run and job timings from the Actions API over a chosen window
- Applies per-runner minute multipliers (Linux, Windows, macOS, larger runners)
- Breaks the total down per workflow, per job, and per matrix leg
- Separates billable execution time from queue wait, so the two are not confused
- Caches fetched runs on disk so a repeated report does not re-walk the API
- Table, CSV and JSON output for a terminal, a spreadsheet or a dashboard

## Stack

Go + go-github, golang.org/x/oauth2, cobra, olekukonko/tablewriter.

## Usage

```bash
gh-workflow-cost --repo owner/example --since 30d --group-by matrix --format csv
```

## License

MIT
