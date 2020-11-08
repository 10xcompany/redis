# Contributing Guide

Thanks for taking time to contribute here.

**Any help is much appreciated!**

## Found a bug?

If you find a bug in the source code, you can help by [submitting an issue](https://github.com/10xcompany/redis/issues/new)
or even better, by [submitting a Pull Request](https://github.com/10xcompany/redis/issues/pulls) with a fix.

## Missing a feature?

You can _request_ a new feature by [submitting an issue](https://github.com/10xcompany/redis/issues/ew) to this GitHub
Repository. If you would like to _implement_ a new feature, please submit an issue with a proposal for your work first,
so we can discuss what is the best way to implement, as well as to be sure nobody else works on that already.

## Submission guidelines

### Submitting an issue

Before you submit an issue, please search the issue tracker, maybe an issue for your problem already exists and the discussion
might inform you of workarounds readily available.

Please provide steps to reproduce for found bug or ideally fork the repository and add failing test that demonstrates what
is wrong. This will help to understand and fix the issue faster.

### Submitting a pull request

Before you submit your pull request consider the following guidelines:

- Search [GitHub](https://github.com/10xcompany/redis/pulls) for an open or closed PR
  that relates to your submission. You don't want to duplicate effort.

- This project aims to have 100% code coverage, so be sure to **include appropriate test cases**.
- Follow defined coding standard, use `yarn lint` command to check it.
- Commit your changes using a descriptive commit message that follows defined commit message conventions.
  Adherence to these conventions is necessary because release notes are automatically generated from these messages.
- Push the code to your forked repository and create a pull request on GitHub.
- If somebody from project contributors suggest changes then:
  - Make the required updates.
  - Re-run all test suites to ensure tests are still passing.
  - Rebase your branch and force push to your GitHub repository (this will update your Pull Request). Basically you can
    use `git commit -a --amend` and `git push --force origin my-fix-branch` in order to keep single commit in the feature
    branch.

That's it! Thank you for your contribution!
