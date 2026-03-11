# Add4x Platform Tracker Setup

This repository can store the source-of-truth templates and label taxonomy, but GitHub Projects
configuration is still a manual org-level step unless Add4x later automates it with the API.

## Recommended Project

- Name: `Add4x Platform Tracker`
- Scope: organization project
- Repos: `restaurant-backend`, `restaurant-admin`, `restaurant-ui`, `restaurant-kds`, `restaurant-pos`

## Custom Fields

Create these single-select fields:

- `Status`
- `Priority`
- `Service`
- `Sprint`
- `Size`

Recommended `Status` options:

- `Needs triage`
- `Ready`
- `In progress`
- `Blocked`
- `In review`
- `Done`

Recommended `Priority` options:

- `Critical`
- `High`
- `Medium`
- `Low`

Recommended `Service` options:

- `Backend`
- `Admin`
- `UI`
- `KDS`
- `POS`
- `Infra`
- `Platform`

Recommended `Size` options:

- `XS`
- `S`
- `M`
- `L`
- `XL`

## Views

Create four views:

- `Board` grouped by `Status`
- `Table` with all key fields visible
- `Roadmap` grouped by `Sprint` and date fields if you use them
- `Triage` filtered to items with `Status = Needs triage`

## Auto-Add Caveats

- Auto-add is configured inside the project, not in this repository.
- You need one auto-add workflow per source repository.
- Auto-add does not backfill existing issues. Import backlog items separately.
- GitHub Free supports only one auto-add workflow. GitHub Team supports five. Confirm the org plan before rollout.

## Auto-Add Rules

Create auto-add workflows for each repository:

- `Add4x/restaurant-backend`
- `Add4x/restaurant-admin`
- `Add4x/restaurant-ui`
- `Add4x/restaurant-kds`
- `Add4x/restaurant-pos`

For each rule, start by adding all new issues, then refine filters later if needed.
