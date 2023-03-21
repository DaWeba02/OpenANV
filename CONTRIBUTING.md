# Contributing to OpenANV

Thanks for taking the time to contribute! :smile:

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Opening Issues](#opening-issues)
- [Writing Documentation](#writing-documentation)
- [Writing Code](#writing-code)
  - [What you need to know before getting started](#what-you-need-to-know-before-getting-started)
  - [Requirements](#requirements)
  - [Getting Started](#getting-started)
  - [Coding Style](#coding-style)
  - [Adding links within code](#Adding-links-within-code)
  - [Tests](#tests)
  - [Packages](#packages)
- [Committing Code](#committing-code)
  - [Branches](#branches)
  - [Pull Requests](#pull-requests)
  - [Dependencies](#dependencies)
- [Reviewing Code](#reviewing-code)
  - [Some rules about Code Review](#Some-rules-about-Code-Review)
  - [Steps to take during Code Review](#Steps-to-take-during-Code-Review)
  - [Code Review Checklist](#Code-Review-Checklist)
  - [Code Review of Dependency Updates](#Code-Review-of-Dependency-Updates)
- [Deployment](#deployment)

## Code of Conduct

All contributors are expecting to abide by our [Code of Conduct](./CODE_OF_CONDUCT.md).

## Opening Issues

**The most important things to do are:**

- Search existing [issues](https://github.com/DaWeba02/OpenANV/issues) for your problem.
- [Update OpenANV](#update-cypress).
- [Gather debugging information](#getting-more-information).
- [Fill out the provided issue template](#fill-out-our-issue-template).
- [Describe your problem, not your solution](#describe-problems)
- [Explain how to reproduce the issue](#reproducibility).

Finally, if you are up to date, supported, have collected information about the problem, and have the best reproduction instructions you can give, you are ready to [open an issue] (https://github.com/DaWeba02/OpenANV/issues).

### Update OpenANV

Before filing a bug, make sure you are up to date. Your issue may have already been fixed. Even if you do not see the issue described as resolved in a newer version, a newer version may help in the process of debugging your issue by giving more helpful error messages.

### Getting more information

For some issues, there are places you can check for more information. This may help you resolve the issue yourself. Even if it doesn't, this information can help us figure out and resolve an issue.

### Fill out our Issue Template

When opening an issue, there is a provided issue template. Fill out the information according to the template. This is information needed for OpenANV to continue forward with your problem. Any issues that don't fill out the issue template will be closed.

### Describe Problems

When you file a feature request or bug, it's best to **describe the problem you are facing first**, not just your desired solution.

Often, your problem may have a lot in common with other similar problems. If we understand your use case, we can compare it to other use cases and sometimes find a more powerful or more general solution which solves several problems at once. Understanding the root issue can let us merge and contextualize things. Sometimes there's already a way to solve your problem that might just not be obvious.

Also, your proposed solution may not be compatible with the direction we want to take the product, but we may be able to come up with another solution which has approximately the same effect and does fit into the product direction.

### Reproducibility

**It is nearly impossible for us to resolve issues if we can not reproduce them. Your best chance of getting a bug looked at quickly is to provide a repository with a reproducible bug that can be cloned and run.**

## Writing Documentation
 
OpenANV documentation lives in a separate repository with its own dependencies and build tools.

## Writing code

Working on your first Pull Request? You can learn how from this free series [How to Contribute to an Open Source Project on GitHub](https://egghead.io/courses/how-to-contribute-to-an-open-source-project-on-github)

### What you need to know before getting started

#### OpenANV and Packages

You need the Visual Studio Package for Node.js and have .NET 6.

### Requirements

You must have the following installed on your system to contribute locally:

- Visual Studio 20xx / Visual Studio Code --> Extension/Package for Node.js
- GIT
- .NET 6

### Coding Style

Please analyze the coding style of @DaWeba02 and try to follow it accordingly.

### Tests

For most packages there are typically unit and integration tests. For UI packages there are E2E and component tests.

## Committing Code

### Branches

The repository has one protected branch:

- `develop` contains the current latest "pre-release" code for OpenANV. This branch is set as the default branch, and all pull requests should be made against this branch.

We do not continuously deploy the OpenANV binary, so `develop` contains all of the new features and fixes that are staged to go out in the next update.

### Pull Requests

- Break down pull requests into the smallest necessary parts to address the original issue or feature. This helps you get a timely review and helps the reviewer clearly understand which pieces of the code changes are relevant.
- When opening a PR for a specific issue already open, please name the branch you are working on using the convention `issue-[issue number]`. For example, if your PR fixes Issue #803, name your branch `issue-803`. If the PR is a larger issue, you can add more context like `issue-803-new-scrollable-area`. If there's not an associated open issue, **[create an issue](https://github.com/DaWeba02/OpenANV/issues)**.
- PRs can be opened before all the work is finished. In fact we encourage this! Please create a [Draft Pull Request](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/about-pull-requests#draft-pull-requests) if your PR is not ready for review. [Mark the PR as **Ready for Review**](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/changing-the-stage-of-a-pull-request#marking-a-pull-request-as-ready-for-review) when you're ready for a OpenANV team member to review the PR.
- Prefix the title of the Pull Request using [semantic-release](https://github.com/semantic-release/semantic-release)'s format using one of the following definitions. Once committed to develop, this prefix will determine the appropriate 'next version' of OpenANV.
  - Changes has user-facing impact:
    - `breaking` - A breaking change that will require a MVB
    - `dependency` - A change to a dependency that impact the user
    - `deprecation` - A API deprecation notice for users
    - `feat` - A new feature
    - `fix` - A bug fix or regression fix.
    - `misc` - a misc user-facing change, like a UI update which is not a fix or enhancement to how OpenANV works
    - `perf` - A code change that improves performance
  - Changes that improves the codebase or system but has no user-facing impact:
    - `chore` - Changes to the build process or auxiliary tools and libraries such as documentation generation
    - `docs` -  Documentation only changes
    - `refactor` - A code change that neither fixes a bug nor adds a feature
    - `revert` - Reverts a previous commit
    - `test` - Adding missing or correcting existing tests
- Fill out the [Pull Request Template](./.github/PULL_REQUEST_TEMPLATE.md) completely within the body of the PR. If you feel some areas are not relevant add `N/A` as opposed to deleting those sections. PRs will not be reviewed if this template is not filled in.
- Please check the "Allow edits from maintainers" checkbox when submitting your PR. This will make it easier for the maintainers to make minor adjustments, to help with tests or any other changes we may need.
![Allow edits from maintainers checkbox](https://user-images.githubusercontent.com/1271181/31393427-b3105d44-ada9-11e7-80f2-0dac51e3919e.png)
- All Pull Requests require a minimum of **one** OpenANV team approvals.
- After the PR is approved, the original contributor can merge the PR (if the original contributor has access).
- When you merge a PR into `develop`, select [**Squash and merge**](https://docs.github.com/en/github/collaborating-with-pull-requests/incorporating-changes-from-a-pull-request/about-pull-request-merges#squash-and-merge-your-pull-request-commits). This will squash all commits into a single commit.

*The only exceptions to squashing are:* 

1. When converting files to another language and there is a clear commit history needed to maintain from the file conversion.
2. When merging a `release/*` branch to `develop`. Individual PRs were already squashed when they were merged to the release branch, and we want that history intact on develop.

### Write Some Tests

If you are adding a new feature or fixing a regression, ensure you add tests for it. Broadly speaking, there are four categories of tests you might consider:

1. Unit tests. These are the fastest and cheapest to execute.
2. Component Tests. These test individual UI components in isolation. They can exhaustively test all expected variations of a component and are faster than E2E tests.
3. E2E/Integration tests. These are between Unit Tests and System Tests when it comes to speed of execution.

When choosing what's most appropriate, consider:

- ease of understanding
- ease of debugging
- resilience to refactoring

It is also worth considering when a failure will be noticed. A unit or component test is likely to be run while the related code is being modified and provides very fast feedback. E2E tests and System Tests are more likely to only fail in CI since they are slower to run.

## Reviewing Code

### Some rules about Code Review

The PR will not be merged if some reviewers have requested changes.

If any of the Pull Request Review guidelines can't be met, a comment should be left by the reviewer with 'Request changes'. The original contributor is responsible for making any updates and request re-review once those changes are addressed.

### Steps to take during Code Review

- Run the code and use it as the end user would.
- Double check the issue and PR description to ensure it is meeting the original requirements.
- Read through every line of changed code (Yes, we know this could be a LOT).
- If you don't understand why some piece of code is required, ask for clarification! Likely the contributor had a reason and can provide the answer quicker than investigating yourself.

### Code Review Checklist

Below are guidelines to help during code review. If any of the following requirements can't be met, leave a comment in the review selecting 'Request changes', otherwise 'Approve'.

#### Functionality

- [ ] The code works and performs its intended function with the correct logic.
- [ ] Performance has been factored in (for example, the code cleans up after itself to not cause memory leaks).
- [ ] The code guards against edge cases and invalid input and has tests to cover it.

#### Maintainability

- [ ] The code is readable (too many nested 'if's are a bad sign).
- [ ] Names used for variables, methods, etc, clearly describe their function.
- [ ] The code is easy to understand and there are relevant comments explaining.
- [ ] New algorithms are documented in the code with link(s) to external docs (flowcharts, w3c, chrome, firefox).
- [ ] There are comments containing link(s) to the addressed issue (in tests and code).

#### Quality

- [ ] The change does not reimplement code.
- [ ] There's not a module from the ecosystem that should be used instead.
- [ ] There is no redundant or duplicate code.
- [ ] There are no irrelevant comments left in the code.
- [ ] There is no irrelevant code to the issue being addressed. If there is, ask the contributor to break the work out into a separate PR.
- [ ] Tests are testing the code's intended functionality in the best way possible.
