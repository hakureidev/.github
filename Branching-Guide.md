# 4 branching workflows for Git

- [Git Flow](#git-flow)
- [Github Flow](#github-flow)
- [Gitlab Flow](#gitlab-flow)
- [One Flow](#one-flow)

## Git Flow
The Git Flow is the most known workflow on this list. It was created by [Vincent Driessen in 2010](http://nvie.com/posts/a-successful-git-branching-model/) and it is based in two main branches with infinite lifetime:

- `master` - this branch contains production code. All development code is merged into `master` in sometime.
- `develop` - this branch contains pre-production code. When the features are finished then they are merged into develop.

During the development cycle, a variety of supporting branches are used:

- `feature-*` - feature branches are used to develop new features for the upcoming releases. May branch off from `develop` and must merge into develop.
- `hotfix-*` - hotfix branches are necessary to act immediately upon an undesired status of `master`. May branch off from `master` and must merge into `master` and `develop`.
- `release-*` - release branches support preparation of a new production release. They allow many minor bug to be fixed and preparation of meta-data for a release. May branch off from `develop` and must merge into `master` and `develop`.

### Advantages

- Ensures a clean state of branches at any given moment in the life cycle of project.
- The branches naming follows a systematic pattern making it easier to comprehend.
- [It has extensions](https://github.com/nvie/gitflow) and support on most used git tools.
- It is ideal when there it needs to be multiple version in production.

### Disadvantages

- The Git history becomes unreadable.
- The master/develop split is considered redundant and makes the Continuous Delivery and the Continuos Integration harder.
- It isn’t recommended when it need to maintain single version in production.

## Github Flow
The GitHub Flow is a lightweight workflow. It was created by [GitHub in 2011](http://scottchacon.com/2011/08/31/github-flow.html) and respects the following 6 principles:

- Anything in the `master` branch is deployable.
- To work on something new, create a branch off frommaster and given a descriptively name(ie: `new-oauth2-scopes`).
- Commit to that branch locally and regularly push your work to the same named branch on the server.
- When you need feedback or help, or you think the branch is ready for merging, open a [pull request](https://help.github.com/send-pull-requests/).
- After someone else has reviewed and signed off on the feature, you can merge it into `master`.
- Once it is merged and pushed to `master`, you can and should _deploy_ immediately.

### Advantages

- it is friendly for the Continuous Delivery and Continuous Integration.
- A simpler alternative to Git Flow
- It is ideal when it needs to maintain single version in production

### Disadvantages

- The production code can become unstable most easily.
- Are not adequate when it needs the release plans.
- It doesn’t resolve anything about deploy, environments, releases, and issues.
- It isn’t recommended when multiple versions in production are needed.

## Gitlab Flow
The GitLab Flow is a workflow created by [GitLab in 2014](https://about.gitlab.com/2014/09/29/gitlab-flow/). It combine [feature-driven development](https://en.wikipedia.org/wiki/Feature-driven_development) and feature branches with issue tracking. The most difference between GitLab Flow and GitHub Flow are the environment branches having in GitLab Flow (e.g. `staging` and `production`) because there will be a project that isn’t able to deploy to production every time you merge a feature branch (e.g. SaaS applications and Mobile Apps).

The GitLab Flow is based on 11 rules:

- Use feature branches, no direct commits on `master`.
- Test all commits, not only ones on `master`.
- Run all the tests on all commits (if your tests run longer than 5 minutes have them run in parallel).
- Perform code reviews before merges into `master`, not afterwards.
- Deployments are automatic, based on branches or tags.
- Tags are set by the user, not by CI.
- Releases are based on tags.
- Pushed commits are never rebased.
- Everyone starts from `master`, and targets master.
- Fix bugs in `master` first and release branches second.
- Commit messages reflect intent.

### Advantages

- It defines how to make the Continuous Integration and Continuous Delivery
- The git history will be cleaner, less messy and more readable (see [why devs prefers squash and merge, instead of only merging, on this article](https://softwareengineering.stackexchange.com/questions/263164/why-squash-git-commits-for-pull-requests))
- It is ideal when it needs to single version in production

### Disadvantages

- It is more complex that the GitHub Flow.
- It can become complex as Git Flow when it needs to maintain multiple version in production.

## One Flow

The One Flow is a proposed alternative in article[ GitFlow considered harmful by Adam Ruka, written in 2015](http://endoflineblog.com/gitflow-considered-harmful). The main condition that needs to be satisfied in order to use OneFlow is that every new production release is based on the previous release. The most difference between One Flow and Git Flow that it not has `develop` branch.

### Advantages
- The git history will be cleaner, less messy and more readable (see [why devs prefers squash and merge, instead of only merging, on this article](https://softwareengineering.stackexchange.com/questions/263164/why-squash-git-commits-for-pull-requests)).
- It is flexible according to team decisions.
- It is ideal when it needs to single version in production.

### Disadvantages

- It isn’t recommended for projects with Continuous Delivery or Continuous Deploy.
- The feature branches make it harder the Continuos Integration
- It isn’t recommended when it needs to maintain single version in production