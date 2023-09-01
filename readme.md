## About

💡 Motivation: I want to check out my repo, make some changes (a single commit), and then create a PR for review.

❓ Purpose: This action handles making a new branch, committing all the changes, and submitting the PR.


## Usage

<!-- Ref: https://stackoverflow.com/questions/72376229/github-actions-is-not-permitted-to-create-or-approve-pull-requests-createpullre -->
> **NOTE**
In order for GitHub Actions to be able to create a pull request, check the checkbox 'Allow GitHub Actions to create and approve pull requests' at https://github.com/OWNER/REPO/settings/actions .

```yml
jobs:
  ...:
    runs-on: ubuntu-latest
    permissions:
      contents: write
      pull-requests: write
    steps:
      - uses: actions/checkout@v3
      - run: ...  # Make all your changes (but don't make commits)
      - uses: scapeville/action-create-PR@v1
        with:
          git_name: name    # Optional
          git_email: email  # Optional
          PR_title: title   # Optional
        env:
          GH_TOKEN: ${{ github.token }}
```
