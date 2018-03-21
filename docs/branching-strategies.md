### The GitHub Flow
As a default, teams should strive to use the GitHub Flow to deliver and develop their code. This simple, standardized approach to contributing to each project will ensure that new members of each team can begin to contribute with minimal ramp-up time. GitHub Flow is a lightweight, branch-based workflow that supports teams and projects where deployments are made regularly:

![GitHub Flow diagram](https://cloud.githubusercontent.com/assets/4215/16997425/a1e816a2-4e72-11e6-9de7-0961ada64ea6.png)

[@schacon](https://github.com/schacon) wrote the [original blog post describing GitHub Flow](http://scottchacon.com/2011/08/31/github-flow.html), including some comparisons to [git-flow](http://nvie.com/posts/a-successful-git-branching-model/), back in 2011.

At GitHub, we use the GitHub Flow pattern to collaborate, deploying feature branches to staging and production environments. As we discussed during our sessions, we use a variety of tools and practices to make this possible. These include [ChatOps](#chatops-hubot), deploy queues, deploy locks, and more.

We've detailed our processes and tooling in our GitHub Engineering Blog post titled ["Deploying Branches to GitHub"](http://githubengineering.com/deploying-branches-to-github-com/).

**Additional resources:**
- [Our interactive GitHub Flow guide](https://guides.github.com/introduction/flow/) [[PDF](https://guides.github.com/pdfs/githubflow-online.pdf)]
- :tv: [Effective GitHubbing: The GitHub Flow](https://vimeo.com/68378254)


### Other workflow tips
- Strive for tightly-scoped, short-lived feature branches (think days, not weeks or longer)
- All new feature branches should be made from `master`. `master` should represent the current production codebase.
- Tight loops (branch from `master`, commits, merge back to `master`) can be a good indicator of healthy workflow, e.g.: https://github.com/github/backup-utils/network
- Use [Releases](https://help.github.com/articles/creating-releases/) to record a history of versions. Upload build artifacts or other compiled binaries as [release attachments](https://developer.github.com/v3/repos/releases/#upload-a-release-asset) instead of checking them into version control.
- Open pull requests early, even before code is written, to discuss implementation. Use [@mentions](https://help.github.com/articles/basic-writing-and-formatting-syntax/#mentioning-users-and-teams) to bring individuals or relevant teams into conversations.

### CI/Automated tests and the Status API
- Separate tests & status updates can provide developers with valuable additional context:
![Multiple status checks](https://cloud.githubusercontent.com/assets/4215/24567070/27e4b768-162a-11e7-964c-ad8801f4beca.png)
- Separating tests can help with parallelization and a "fail fast" approach to test pipelines.
- Even if your test pipeline is triggered by a single outbound webhook, you can configure component steps of your pipeline to [report statuses back to GitHub](https://developer.github.com/v3/repos/statuses/) separately.

### Code review
- Requiring [Pull Request Reviews](https://help.github.com/enterprise/user/articles/about-pull-request-reviews/) means that contributors can't merge a pull request without another contributor's :+1:.
- Developers should [request reviews from specific collaborators](https://help.github.com/enterprise/2.9/user/articles/requesting-a-pull-request-review/) when they're ready to merge.
