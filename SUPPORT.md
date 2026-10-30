# Getting help

Questions and bug reports go to the issues of the public repositories:
**[`panel`](https://github.com/nx-panel/panel/issues/new/choose)** for the Panel, the installer, subscriptions and
anything you are not sure about, and **[`node`](https://github.com/nx-panel/node/issues/new/choose)** for a problem that is
only on a node.

Pick the route that matches what you have:

| You have | Go to |
| --- | --- |
| A question about installing, configuring or using NX | Read [the documentation](https://docs.nx-panel.org), or [open an issue](https://github.com/nx-panel/panel/issues/new/choose) and pick **Question** |
| Something that looks broken | A bug report on [`panel`](https://github.com/nx-panel/panel/issues/new/choose), or on [`node`](https://github.com/nx-panel/node/issues/new/choose) when only a node is affected |
| An idea for something NX should do | [A feature request on `panel`](https://github.com/nx-panel/panel/issues/new/choose) |
| A security vulnerability | **Not an issue** — [open a private advisory](https://github.com/nx-panel/.github/security/advisories/new). See [SECURITY.md](SECURITY.md) |
| A licensing or purchasing question | The **License** page in the Panel admin UI, visible to the main admin, has the current contact route |

## Before you open an issue

Most of the time spent on a support issue is spent asking for things that could
have been in the first message. Please include:

- **Versions.** `nx-panel version` and `nx-node version`, or the image
  tags you are running. They are versioned separately, so both matter.
- **How it is installed** — the install script, Docker, or by hand — and the
  operating system.
- **What you expected and what happened instead.** "It does not work" cannot be
  investigated.
- **Logs from around the failure**, not the whole file:
  ```bash
  journalctl -u nx-panel -n 100 --no-pager    # on the panel host
  journalctl -u nx-node  -n 100 --no-pager    # on the node
  docker compose logs --tail 100                  # under Docker
  ```

**Redact before pasting.** Subscription URLs, install tokens, setup tokens,
licence keys, private keys and database DSNs are credentials, and an issue is
public. Replace them with `REDACTED` rather than trimming a few characters off
the end — a partial secret is still a leaked secret.

## Things that are usually not bugs

- **The panel returns 404 for everything.** Setup has not been finished. Open the
  link the installer printed, or run `nx-panel setup-token` for a new one.
- **You cannot reach the panel after changing a setting.** Nothing is lost — the
  port, domain and base path are all writable offline with
  `nx-panel config set`, and [the documentation](https://docs.nx-panel.org) has the exact commands.
- **A node shows offline.** Almost always a firewall or security group that does
  not let the panel reach TCP 62050 on the node.
- **A node was reinstalled and the panel refuses it.** A reinstall means a new
  node certificate, and the panel is still pinning the old one. Delete the node
  in the panel and add it again.
- **You have hit 25 users or 1 node.** That is the free tier, working as
  intended, not a defect.

## What to expect

This is a small project. Issues are read, and the ones that come with versions,
logs and reproduction steps are the ones that get fixed first. Nobody is on call,
and there is no response-time commitment on support issues — security reports are
the exception and have their own timeline in [SECURITY.md](SECURITY.md).
