## About

💡 Motivation: I want to check out my repo, make some changes (a single commit), and then create a PR for review.

❓ Purpose: This action handles making a new branch, committing all the changes, and submitting the PR.


## Usage

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