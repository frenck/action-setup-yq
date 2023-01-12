# 🚀 Frenck's Github Action: yq

[![GitHub Release][releases-shield]][releases]
![Project Stage][project-stage-shield]
![Project Maintenance][maintenance-shield]
[![License][license-shield]](LICENSE.md)

[![Sponsor Frenck via GitHub Sponsors][github-sponsors-shield]][github-sponsors]

🚀 Frenck's GitHub Action for setting up yq.

## About

A very simple and easy to use GitHub Action for setting up [yq][yq] for use in
your GitHub Actions.

All it does is installing it, so you can use it for reading or manipulating
YAML files in your GitHub actions.

## Usage

```yaml
name: Example
on: [push, pull_request]
jobs:
  example:
    name: Example
    runs-on: ubuntu-latest
    steps:
      - name: 🏗 Set up yq
        uses: frenck/action-setup-yq@v1
        with:
          token: ${{ secrets.GITHUB_TOKEN }}
      - name: 🚀 Use yq
        run: yq --version
```

## Arguments

|   Input   |                    Description                    |   Usage    |
| :-------: | :-----------------------------------------------: | :--------: |
|  `token`  | The GitHub token to use for making API requests.  | _Required_ |
| `version` | The yq version to install. The latest if omitted. | _Optional_ |

## Outputs

|  Output   |              Description              |   Usage    |
| :-------: | :-----------------------------------: | :--------: |
| `version` | The version of yq that was installed. | _Optional_ |

## Real-world examples

The following repositories are using this GitHub Action, and thus provide
you with some real-world uses of this GitHub Action.

- [Home Assistant Community Add-ons](https://github.com/hassio-addons/repository)

Are you using this GitHub Action? Feel free to open up a PR to add your
configuration to this list 😍

## Versions & Updating

You can specify which version of this GitHub Action your workflow should use.
And even allowing for using the latest major or minor version.

For example; this will use release `v1.1.1` of a GitHub Action:

```yaml
- name: 🏗 Set up yq
  uses: frenck/action-setup-yq@v1.1.1
```

While the following example, will use the `v1.1.x` minor release, for example
if `v1.1.2` is the latest releases (starting with `v1.1`), this will run
`v1.1.2`:

```yaml
- name: 🏗 Set up yq
  uses: frenck/action-setup-yq@v1.1
```

As in the examples throughout the documentation, the following example is
locked on major version, meaning any `v1.x.x` latest version will be used,
as long as it is version 1.

```yaml
- name: 🏗 Set up yq
  uses: frenck/action-setup-yq@v1
```

### Automatically update using Dependabot

The advantage of locking against a more specific version, is that it prevents
surprises if an issue or breaking changes were introduced in a newer release.

The disadvantage of being more specific, is that it requires you to keep things
up to date. Fortunately, GitHub has a tool for that, called: Dependabot.

Dependabot can automatically open a pull request on your repository to update
this Action for you. You can instantly see if the new version works (as the
pull request shows the success or failure status) and you can decide to
merge it in by hitting the merge button. Quick, easy and always up2date.

To enable Dependabot, create a file called `.github/dependabot.yaml`:

```yaml
version: 2
updates:
  - package-ecosystem: "github-actions"
    directory: "/"
    schedule:
      interval: daily
```

Your all set! Dependabot will now check (and update) your GitHub actions
every day. 🤩

## Changelog & Releases

This repository keeps a change log using [GitHub's releases][releases]
functionality.

Releases are based on [Semantic Versioning][semver], and use the format
of `MAJOR.MINOR.PATCH`. In a nutshell, the version will be incremented
based on the following:

- `MAJOR`: Incompatible or major changes.
- `MINOR`: Backwards-compatible new features and enhancements.
- `PATCH`: Backwards-compatible bugfixes and package updates.

## Contributing

This is an active open-source project. We are always open to people who want to
use the code or contribute to it.

We've set up a separate document for our
[contribution guidelines](CONTRIBUTING.md).

Thank you for being involved! :heart_eyes:

## Authors & contributors

The original setup of this repository is by [Franck Nijhof][frenck].

For a full list of all authors and contributors,
check [the contributor's page][contributors].

## License

MIT License

Copyright (c) 2021-2022 Franck Nijhof

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

[contributors]: https://github.com/frenck/action-setup-yq/graphs/contributors
[frenck]: https://github.com/frenck
[github-sponsors-shield]: https://frenck.dev/wp-content/uploads/2019/12/github_sponsor.png
[github-sponsors]: https://github.com/sponsors/frenck
[license-shield]: https://img.shields.io/github/license/frenck/action-setup-yq.svg
[maintenance-shield]: https://img.shields.io/maintenance/yes/2022.svg
[project-stage-shield]: https://img.shields.io/badge/project%20stage-production%20ready-brightgreen.svg
[releases-shield]: https://img.shields.io/github/release/frenck/action-setup-yq.svg
[releases]: https://github.com/frenck/action-setup-yq/releases
[semver]: http://semver.org/spec/v2.0.0.html
[yq]: https://github.com/mikefarah/yq
