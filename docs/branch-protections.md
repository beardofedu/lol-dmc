### Branch Protection Enforcements
Below are the required, standard settings to enforce merge policies across all repositories in the Dow Organization. While each team can choose to enforce additional parameters, these should be enforced at a minimum. Additional information regarding other options for defining protected branches and mergeability can be found [here](https://help.github.com/articles/defining-the-mergeability-of-pull-requests/).

- Use [protected branches](https://help.github.com/articles/about-protected-branches/) in all repositories
  - Protect at least the `master` branch
- Require [Pull Request Reviews](https://help.github.com/enterprise/user/articles/about-pull-request-reviews/) for all feature branches
  - Enable `Dismiss stale pull request approvals...` to ensure that when new, reviewable commits are pushed, all previous approvals are invalid
- Configure automated tests/CI to update GitHub via the Status API
  - Configure [required status checks](https://help.github.com/articles/about-required-status-checks/) for key tests, such as integration tests. At a minimum, mergeable code should build successfully, and each team can choose to implement additional CI tests as needed
- Enforce branch protections for Admins by selecting `Include Administrators`
