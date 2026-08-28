# Getting help

Nexora's source repositories are private, so **[this repository's issue
tracker](https://github.com/Nexora-VPN/.github/issues) is where questions and
bug reports about the Panel and the Node go**. There is nowhere else to file
them; the tracker here is not only for the organisation files.

Pick the route that matches what you have:

| You have | Go to |
| --- | --- |
| A question about installing, configuring or using Nexora | [Open an issue](https://github.com/Nexora-VPN/.github/issues/new/choose) and pick **Question**, or read the installation guide that shipped with your copy |
| Something that looks broken | [Open a bug report](https://github.com/Nexora-VPN/.github/issues/new/choose) |
| An idea for something Nexora should do | [Open a feature request](https://github.com/Nexora-VPN/.github/issues/new/choose) |
| A security vulnerability | **Not an issue** — [open a private advisory](https://github.com/Nexora-VPN/.github/security/advisories/new). See [SECURITY.md](SECURITY.md) |
| A licensing or purchasing question | The **License** page in the Panel admin UI, visible to the main admin, has the current contact route |

## Before you open an issue

Most of the time spent on a support issue is spent asking for things that could
have been in the first message. Please include:

- **Versions.** `nexora-panel version` and `nexora-node version`, or the image
  tags you are running. They are versioned separately, so both matter.
- **How it is installed** — the install script, Docker, or by hand — and the
  operating system.
- **What you expected and what happened instead.** "It does not work" cannot be
  investigated.
- **Logs from around the failure**, not the whole file:
  ```bash
  journalctl -u nexora-panel -n 100 --no-pager    # on the panel host
  journalctl -u nexora-node  -n 100 --no-pager    # on the node
  docker compose logs --tail 100                  # under Docker
  ```

**Redact before pasting.** Subscription URLs, install tokens, setup tokens,
licence keys, private keys and database DSNs are credentials, and an issue is
public. Replace them with `REDACTED` rather than trimming a few characters off
the end — a partial secret is still a leaked secret.

## Things that are usually not bugs

- **The panel returns 404 for everything.** Setup has not been finished. Open the
  link the installer printed, or run `nexora-panel setup-token` for a new one.
- **You cannot reach the panel after changing a setting.** Nothing is lost — the
  port, domain and base path are all writable offline with
  `nexora-panel config set`, and the installation guide has the exact commands.
- **A node shows offline.** Almost always a firewall or security group that does
  not let the panel reach TCP 62050 on the node.
- **A node was reinstalled and the panel refuses it.** A reinstall means a new
  node certificate, and the panel is still pinning the old one. Delete the node
  in the panel and add it again.
- **You have hit 1 inbound, 1 outbound, 1 endpoint, 1 user, 1 node.** That is the
  free tier, working as intended, not a defect.

## What to expect

This is a small project. Issues are read, and the ones that come with versions,
logs and reproduction steps are the ones that get fixed first. Nobody is on call,
and there is no response-time commitment on support issues — security reports are
the exception and have their own timeline in [SECURITY.md](SECURITY.md).
