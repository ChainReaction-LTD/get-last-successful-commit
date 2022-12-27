# get-last-successful-commit

This action returns the commit hash for the last successful run of the current workflow on:
* The current branch for the given _event-name_ (default: pull_request).
* The parent branch for the given _parent-envent-name_ (default: push) - when last successful run for current branch for the given _event-name_ CANNOT be found.

This is especially useful when we have a workflow where we need to know what changed in a given branch between two commits, so we can execute an incremental CI.

## Usage
```yaml
- uses: ChainReaction-LTD/get-last-successful-commit@v1
  with:
    # Event name that triggered the workflow for the current branch (for query)
    # Default: pull_request
    event-name: pull_request

    # Parent of the current branch to get last successful commit from (fallback)
    # Rquired
    parent-branch: ''

    # Event name that triggered the workflow for the parent branch (for query)
    # Default: push
    parent-event-name: push

    # GitHub personal access token (with repo scope for private repositories and public_repo scope for public repositories)
    # Required
    github-token: ''
```
