# Nexora-VPN/.github

Organisation-level files for [Nexora VPN](https://github.com/Nexora-VPN). GitHub treats a repository named `.github` specially: the profile in `profile/` is shown on the organisation page, and the community health files below become the default for every repository in the organisation that does not carry its own copy.

| Path | Purpose |
|---|---|
| [`profile/README.md`](profile/README.md) | The organisation profile, rendered at the top of <https://github.com/Nexora-VPN>. |
| [`SECURITY.md`](SECURITY.md) | How to report a vulnerability — privately, through [GitHub advisories on this repository](https://github.com/Nexora-VPN/.github/security/advisories/new), for every Nexora component. |
| [`CONTRIBUTING.md`](CONTRIBUTING.md) | Where bug reports, feature requests and pull requests go, and the conventions they follow. |
| [`SUPPORT.md`](SUPPORT.md) | Where to get help, per kind of question. |
| [`.github/ISSUE_TEMPLATE/`](.github/ISSUE_TEMPLATE/) | Issue forms — *Bug report*, *Feature request* and *Question* — plus `config.yml`, which adds the security and support links to the "new issue" chooser and keeps blank issues enabled. |
| [`.github/PULL_REQUEST_TEMPLATE.md`](.github/PULL_REQUEST_TEMPLATE.md) | Pull request checklist. |

No Nexora repository is public except this one, so **this repository's [issue tracker](https://github.com/Nexora-VPN/.github/issues) is the public place to report Panel and Node bugs**, and its security advisories are the single private intake for vulnerabilities in any component. Private vulnerability reporting is enabled here for that reason; keep it on.

`panel` and `node` — the distribution repositories holding the releases, images, installer and documentation — are private for now. **When they are made public, move bug reports there**: `SUPPORT.md`, `CONTRIBUTING.md` and `SECURITY.md` all route reports here today and will need the product links instead. Advisories stay here either way, because an advisory filed on a public product repository would be readable while the flaw is still unfixed.

## Editing

- Push to `main`; GitHub picks the change up immediately, there is no build step.
- This repository is **public**; every other Nexora repository is private, including the `panel` and `node` distribution repositories. Keep everything at product level and do not name or link a private repository — such a link is a 404 for everyone outside the organisation.
- Community health files are looked up in the `.github/` folder, then the root, then `docs/` — except issue forms, which GitHub only reads from `.github/ISSUE_TEMPLATE/`. A repository that has *any* file in its own `.github/ISSUE_TEMPLATE/` ignores all of the defaults from here.
- A label set by an issue form (`bug`, `enhancement`) has to exist in **every** repository where the form is used, not only in this one, or the label is silently dropped.
- The logo is the organisation avatar (`https://avatars.githubusercontent.com/u/304456640`), so changing the avatar in the organisation settings updates the profile too.
