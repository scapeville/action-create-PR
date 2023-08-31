## Motivation

I want to check out my repo, make some changes (a single commit), and then create a PR for review.

## About

this action provide a simple and 


the straightforward way making PR: 


how to use:

1. do actions/checkout@v3
2. make all changes you want (but do NOT make commit)
3. use this action to handle the: making new branch, committing, and submitting the PR.



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
      - uses: scapeville/action-create-PR@main
        with:
          git_name: testing action-create-PR
          git_email: your@email
          PR_title: foo bar
        env:
          GH_TOKEN: ${{ github.token }}
```