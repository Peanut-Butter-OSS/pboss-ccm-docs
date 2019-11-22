.. _git_standards:

Git Standards
=============

As a general rule the project utilises a "Feature Branch" approach for development work. With this approach, the project has the following permanent branches:

* master: This branch is always stable and tested. It is deployed to QA at the end of each sprint.
* dev: This branch changes only when code-reviewed features are merged into it. It is deployed to the DEV environment after each pull request.

Developers will create temporary branches on a per-feature basis for each feature that is being worked on.

Feature Branches
----------------
A feature branch MUST relate to a JIRA issue (either at the level of sub-task or at the level of user-story).

The branch should not typically exist for longer than 1 week.

As a normal rule all feature branches should be deleted at the each of each sprint to avoid a proliferation of feature branches.

To create a feature branch:
 * Open the relevant JIRA task
 * Select the Create Branch option in JIRA
 * Now checkout the branch on your local environment (Note: you may need to do a *git fetch origin* first, if you cannot immediately pull the branch locally)
 
Pull Requests
-------------
To enforce a code review process, the ability to merge code into the dev branch will be limited to 2 individuals.

Nobody should merge code directly into the dev branch, it must be done as part of a pull request which is then reviewed and merged into dev by one of the selected individuals.

To create a pull request, the following steps should be taken:
 * Ensure your code is stable in your source
 * Checkout the dev branch
 * Pull the latest dev branch
 * Checkout your source branch
 * git merge dev, to ensure all the latest dev code is in your branch
 * Resolve any merge conflicts that might arise
 * Run a local build to confirm all is fine
 * Do some manual tests locally to verify that your new functionality works as expected
 * Run the BDD tests using the @PullRequest tag to do some basic checks on your local branch
 * Open up BitBucket and create the pull request

When merging a pull request, the following steps should be taken:
 * Note: Ideally a pull request should only be performed on the SARB network to ensure a full BDD test can be run
 * Review the notes in the Pull request on BitBucket
 * Checkout the source branch locally
 * git pull, to ensure the latest version of the source branch is available
 * Run a local build. mvn clean install ...
 * Do some quick checks to confirm the build is fine
 * Checkout the dev branch
 * Pull the latest dev branch
 * Checkout your source branch
 * git merge dev, to ensure all the latest dev code is in your branch
 * Resolve any merge conflicts that might arise
 * Run a local build to confirm all is fine
 * Do some manual tests locally to verify that the new functionality works as expected
 * Run the full suite of BDD tests to ensure the code base is still stable
 * If all is fine, open up BitBucket and click the Merge Button
 * Once merged Checkout the dev branch locally
 * git remote prune origin, to remove any deleted branched from your local index
 * Pull the latest dev branch, this should now include the new merged code
 * git push tfs dev






