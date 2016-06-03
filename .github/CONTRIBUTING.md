# How to Contribute

Third-party patches are essential for keeping open-source software great. In the spirit of keeping it as simple as possible to contribute changes that get things working in your environment, here are a few guidelines that contributors should follow.  As [Nicholas Gallagher](http://github.com/necolas/normalize.css/blob/master/CONTRIBUTING.md) put it in his contributing guidelines:

> Following these guidelines helps to communicate that you respect the
> time of the developers managing and developing […]. In return, they
> should reciprocate that respect in addressing your issue or
> assessing your patches and features.

## Table of Contents

1. [Getting Started](#getting-started)
2. [Bug Reports](#bug-reports)
3. [Feature Requests](#feature-requests)
4. [Pull Requests](#pull-requests)
5. [Gotchas](#gotchas)
6. [Deployments](#deployments)
7. [Owners](#owners)
8. [Code of Conduct](#code-of-conduct)
9. [Additional Resources](#additional-resources)

## Getting Started

1. Make sure you have a [GitHub account](https://github.com/signup/free).
2. Please [ask before](https://twitter.com/iamnewton) making significant changes.  I'd hate for you to put in a lot of work for something that doesn't align with the vision of this project.

### Environment Set Up

1. `sudo gem install overcommit` - In the same sense for code consistency, we ask that you install and setup [Overcommit](https://github.com/brigade/overcommit).  This allows us to use Git Hooks to prevent bad code/untested code and unoptimized code from seeping into the system.
2. In order to keep a consistent code base, we ask that you install and set up [EditorConfig](http://editorconfig.org/) using one of the editor plugins.
3. Clone the repository to your desired location.
4. `npm install` - This is currently used for the build process.

## Bug Reports

Bugs are small, testable and demonstratable problems caused by the code.  A good report will be able to easily outline the problem and steps to recreate.  If you're going to submit a bug, please verify you've done everything on this list.

1. [Search](https://github.com/chrisopedia/mlb-logos/issues?utf8=%E2%9C%93&q=is%3Aissue+is%3Aopen) for the issue.  This means you may have to read through the issue(s) in order to determine if your particular issue has already been created.
2. Check if the issue has been fixed by trying to reproduce the issue in a fresh clone of the repository off the `master` branch.
3. If you've followed the above, and you're still seeing the problem, congratulations, you've found a bug.

### Create a Ticket

Now its time to [submit a ticket](https://github.com/chrisopedia/mlb-logos/issues/new).  Bug reports should be thorough and not leave anyone wondering or questioning what you were thinking.  No one should have to ask you anything or require further clarification.  The title should be concise and descriptive; anyone should be able to know what you're issue is at a glance.  For the description section, there are some very specific fields that should be within there.  The first few lines should be a description or summary of the issue; don't be afraid to go into detail.  No one ever said too much detail was a problem, and if they did, it wasn't me; you can follow the [Issues Template](https://github.com/chrisopedia/mlb-logos/blob/master/ISSUE_TEMPLATE.md). A few other things should be included are listed as such:

1. **OS & version**: Always include the OS(es) and version(s) where you found the issue.  If, for example its Mavericks, you can put OSX 10.9.1.
2. **Test Results**: If there is a fail in a particular test, include the name of the test, otherwise list as "Passed".
3. **Steps to Reproduce**: Please include the steps you followed to find this bug.  This will make my life so much easier to help fix the issue.  Screenshots can be a big help as well along with the steps.
4. **Line(s) of Code**: Definitely not a requirement, but doesn't hurt if you've already pin pointed the issue.
5. **Browser(s) Version(s)**: What version are you running?

For the comment section, please follow the example below and you'll be on the right path.  Let's assume that a you're trying to save a seat and its throwing an error, here's an example.

### Example

```markdown
Clone script is throwing "repo not found" error

**OS**: OSX 10.8.3
**Steps to Reproduce**:
1.  Load <url>
2.  Notice that script throws error suggesting repo is not found, although repo is on http://chrisopedia.github.io/mlb-logos
**Line(s) of Code**: 18
**Library Version**: 0.1.0
**Browser(s) Version(s)**: All browsers, but founded initially in Chrome 38.0.2125.111
```

## Pull Requests

If you're unfamiliar with the Github flow, please [read this guide](https://guides.github.com/introduction/flow/index.html).

### The Process (for contributors)

1. Fork the repo using the [Fork button](https://github.com/chrisopedia/mlb-logos#fork-destination-box)
2. Clone the repo (`git clone https://github.com/<github-user>/legion`)
3. Change into the directory you just cloned.
4. Add your fork as a remote (`git remote add <github-user> https://github.com/<github-user>/legion`)
5. Create your feature branch (`git checkout -b feature/my-new-feature`)
6. Commit your changes (`git commit`), follow the format suggested below.  Please don't use the shortcut flag `git commit -m <message>`.
7. Push to the branch (`git push <github-user> feature/my-new-feature`)
8. Create new [Pull Request](https://github.com/chrisopedia/mlb-logos/compare) using the [Pull Request Template](https://github.com/chrisopedia/mlb-logos/blob/master/PULL_REQUEST_TEMPLATE.md)

### The Process (for maintainers)

1. Clone the repo (`git clone https://github.com/chrisopedia/mlb-logos`)
2. If you've cloned previously, then get latest changes.

    ```bash
    $ git checkout master
    $ git pull origin master
    ```

3. Create your feature branch (`git checkout -b feature/my-new-feature`)
4. Commit your changes (`git commit`), follow the format suggested below.  Please don't use the shortcut flag `git commit -m <message>`.
5. Push to the branch (`git push origin feature/my-new-feature`)
6. Create new [Pull Request](https://github.com/chrisopedia/mlb-logos/compare) using the [Pull Request Template](https://github.com/chrisopedia/mlb-logos/blob/master/PULL_REQUEST_TEMPLATE.md)

**IMPORTANT**: Every patch and subsequent message should have a bug attached.  If there is no ticket, no work should be done.

### Gotchas
- Please avoid working directly on the `master` branch.
- Make commits of logical units.
- Check for unnecessary whitespace with `git diff --check` before committing.
- Make sure your commit messages are in the [proper format](http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html).

```diff
    Create new feature (use CRUD-style language)

    More detailed explanatory text, if necessary.  Wrap it to about 72
    characters or so.  In some contexts, the first line is treated as the
    subject of an email and the rest of the text as the body.  The blank
    line separating the summary from the body is critical (unless you omit
    the body entirely); tools like rebase can get confused if you run the
    two together.

    Write your commit message in the imperative: "Fix bug" and not "Fixed bug"
    or "Fixes bug."  This convention matches up with commit messages generated
    by commands like git merge and git revert. I prefer to use CRUD-style
    messaging; all messages should start with either Create, Read (hardly ever
    used), Update & Delete.

    Further paragraphs come after blank lines.

    - Bullet points are okay, too
    - Typically a hyphen or asterisk is used for the bullet, preceded by a
      single space, with blank lines in between, but conventions vary here
    - Use a hanging indent
```

## Deployments

After your pull request has been given the green light, its time to prepare
   for the deployment.

### Preparation

1. Merge your feature branch into master
2. Update the version number in the
   [package.json](https://github.com/chrisopedia/mlb-logos/blob/master/package.json#L9)
3. Run `npm run dist` to compile a new version of framework.  This will build
   all files.
4. Once verified, commit your changes into master with the message as 'Bump to
   version <X.Y.Z>'
5. Tag the release by running `git tag <X.Y.Z.>`
6. Push to the origin, including the tags by running `git push origin master
   --tags`

## Gotchas

- Please avoid working directly on the `master` branch.
- Make commits of logical units.
- Check for unnecessary whitespace with `git diff --check` before committing.
- Update the OWNERS file.  See [OWNERS](#owners) below for more information.
- Make sure your commit messages are in the [proper format](http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html).

```diff
    Create new feature (use CRUD-style language)

    More detailed explanatory text, if necessary.  Wrap it to about 72
    characters or so.  In some contexts, the first line is treated as the
    subject of an email and the rest of the text as the body.  The blank
    line separating the summary from the body is critical (unless you omit
    the body entirely); tools like rebase can get confused if you run the
    two together.

    Write your commit message in the imperative: "Fix bug" and not "Fixed bug"
    or "Fixes bug."  This convention matches up with commit messages generated
    by commands like git merge and git revert. I prefer to use CRUD-style
    messaging; all messages should start with either Create, Read (hardly ever
    used), Update & Delete.

    Further paragraphs come after blank lines.

    - Bullet points are okay, too
    - Typically a hyphen or asterisk is used for the bullet, preceded by a
      single space, with blank lines in between, but conventions vary here
    - Use a hanging indent

    Issue: #<number of issue>
```

## OWNERS

The developers on the Chromium project have created an interesting of attaching reviewers to a particular set of code.  The concept is best described by them…

> OWNERS files are a way of specifying a set of reviewers whose review is
> required to modify certain areas of code<sup>[1][owners]</sup>

You can read more at [Chromium Projects][owners] site, but the basic concept is that if you edit by either changing existing or creating new functionality, then add your name to the OWNERS file in the parent directory that encompasses your feature.  If you've made a global change that affects the entire repository, then you should add your name to the root OWNERS file.

## Code of Conduct

As contributors and maintainers of this project, and in the interest of fostering an open and welcoming community, we pledge to respect all people who contribute through reporting issues, posting feature requests, updating documentation, submitting pull requests or patches, and other activities.

We are committed to making participation in this project a harassment-free experience for everyone, regardless of level of experience, gender, gender identity and expression, sexual orientation, disability, personal appearance, body size, race, ethnicity, age, religion, or nationality.

Examples of unacceptable behavior by participants include:

* The use of sexualized language or imagery
* Personal attacks
* Trolling or insulting/derogatory comments
* Public or private harassment
* Publishing other's private information, such as physical or electronic addresses, without explicit permission
* Other unethical or unprofessional conduct.

Project maintainers have the right and responsibility to remove, edit, or reject comments, commits, code, wiki edits, issues, and other contributions that are not aligned to this Code of Conduct. By adopting this Code of Conduct, project maintainers commit themselves to fairly and consistently applying these principles to every aspect of managing this project. Project maintainers who do not follow or enforce the Code of Conduct may be permanently removed from the project team.

This code of conduct applies both within project spaces and in public spaces when an individual is representing the project or its community.

Instances of abusive, harassing, or otherwise unacceptable behavior may be reported by opening an issue or contacting one or more of the project maintainers.

This Code of Conduct is adapted from the [Contributor Covenant](http://contributor-covenant.org), version 1.2.0, available at [http://contributor-covenant.org/version/1/2/0/](http://contributor-covenant.org/version/1/2/0/)

## Additional Resources

- [General GitHub documentation](http://help.github.com/)
- [GitHub Send Pull Request Documentation](http://help.github.com/send-pull-requests/)
- [GitHub Using Pull Request Documentation](https://help.github.com/articles/using-pull-requests/)
- [Forking a Github Repo](http://help.github.com/fork-a-repo/)

[owners]: http://www.chromium.org/developers/owners-files
