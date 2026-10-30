# nx-panel/.github

Organisation-level files for [NX](https://github.com/nx-panel). GitHub treats a repository named `.github` specially: the profile in `profile/` is shown on the organisation page, and the community health files below become the default for every repository in the organisation that does not carry its own copy.

| Path | Purpose |
|---|---|
| [`profile/README.md`](profile/README.md) | The organisation profile, rendered at the top of <https://github.com/nx-panel>. |
| [`SECURITY.md`](SECURITY.md) | How to report a vulnerability — privately, through [GitHub advisories on this repository](https://github.com/nx-panel/.github/security/advisories/new), for every NX component. |
| [`CONTRIBUTING.md`](CONTRIBUTING.md) | Where bug reports, feature requests and pull requests go, and the conventions they follow. |
| [`SUPPORT.md`](SUPPORT.md) | Where to get help, per kind of question. |
| [`.github/ISSUE_TEMPLATE/`](.github/ISSUE_TEMPLATE/) | Issue forms — *Bug report*, *Feature request* and *Question* — plus `config.yml`, which adds the security and support links to the "new issue" chooser and keeps blank issues enabled. |
| [`.github/PULL_REQUEST_TEMPLATE.md`](.github/PULL_REQUEST_TEMPLATE.md) | Pull request checklist. |

The Panel's and the Node's source is private; their public repositories, [`panel`](https://github.com/nx-panel/panel) and [`node`](https://github.com/nx-panel/node), hold the releases, images, installer and documentation. **Bug reports, feature requests and questions go to the issues of `panel` and `node`**, through the forms in this repository. This repository has no issues of its own; its security advisories are the single private intake for vulnerabilities in any component. Private vulnerability reporting is enabled here for that reason; keep it on.

Advisories stay here rather than on `panel` or `node`, because an advisory filed on a public product repository would be readable while the flaw is still unfixed. The issue forms here are used by `panel` and `node` as long as neither has its own `.github/ISSUE_TEMPLATE/`.

## Editing

- Push to `main`; GitHub picks the change up immediately, there is no build step.
- This repository is **public**, like `panel`, `node`, the addons and their kit; the Panel's and the Node's source repositories are private. Keep everything at product level and do not name or link a private repository — such a link is a 404 for everyone outside the organisation.
- Community health files are looked up in the `.github/` folder, then the root, then `docs/` — except issue forms, which GitHub only reads from `.github/ISSUE_TEMPLATE/`. A repository that has *any* file in its own `.github/ISSUE_TEMPLATE/` ignores all of the defaults from here.
- A label set by an issue form (`bug`, `enhancement`) has to exist in **every** repository where the form is used, not only in this one, or the label is silently dropped.
- The logo is the organisation avatar (`https://avatars.githubusercontent.com/u/349063115`), so changing the avatar in the organisation settings updates the profile too.
