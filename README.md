# Add4x/.github

Organization-wide defaults and SDLC configuration for the Add4x restaurant platform.

## Important Constraint

This repository must be `public` to apply default issue templates, pull request templates,
and community health files across the organization on GitHub.com.

If the Add4x org is on GitHub Enterprise Cloud, `internal` also works. `private` does not.

## What's Here

| Path | Purpose |
|------|---------|
| `profile/README.md` | Organization profile README |
| `.github/ISSUE_TEMPLATE/` | Default issue forms for repos without local templates |
| `.github/PULL_REQUEST_TEMPLATE.md` | Default PR template |
| `.github/labels.yml` | Source of truth for the shared 34-label taxonomy |
| `.github/workflows/sync-labels.yml` | Syncs labels to all restaurant repos from `labels.yml` |
| `CONTRIBUTING.md` | Default contribution guidance |
| `CODE_OF_CONDUCT.md` | Default community standards |
| `SECURITY.md` | Security reporting policy |
| `SUPPORT.md` | Default support guidance surfaced in new issue flow |
| `PROJECT_SETUP.md` | Manual setup guide for the org GitHub Project |

## Label System

The shared taxonomy contains 34 labels in six groups:

- `type:` for work classification
- `priority:` for urgency
- `status:` for workflow state
- `scope:` for service ownership
- `size:` for rough sizing
- special labels for onboarding and risk signaling

The sync workflow runs on changes to `labels.yml`, on manual dispatch, and every Monday at `06:00 UTC`.
It is configured to delete labels that are not in the source-of-truth file.

## Template Behavior

Defaults from this repository apply only when a target repository does not define its own
equivalent files. In particular, if a repo has anything in its own `.github/ISSUE_TEMPLATE/`
directory, GitHub ignores the org-level default issue templates for that repo.

At the time this repo was scaffolded, these repos did not define local issue or PR templates:

- `restaurant-backend`
- `restaurant-admin`
- `restaurant-ui`
- `restaurant-kds`
- `restaurant-pos`

## Label Sync Auth

`sync-labels.yml` expects an org or repo secret named `ORG_GITHUB_TOKEN` with permission to
manage labels in:

- `Add4x/restaurant-backend`
- `Add4x/restaurant-admin`
- `Add4x/restaurant-ui`
- `Add4x/restaurant-kds`
- `Add4x/restaurant-pos`

A classic PAT with `repo` scope works. A fine-grained token also works if it has repository
administration or issues write access for each target repository.
