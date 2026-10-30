# Security policy

NX sits between operators and their users' traffic, so a vulnerability here
is rarely cosmetic. Reports are welcome and taken seriously.

## Reporting a vulnerability

**[Open a private advisory on this repository.](https://github.com/nx-panel/.github/security/advisories/new)**

That one form covers **every** NX component — Panel, Node, the installers,
the container images and the subscription pages. Reporting it here rather than
anywhere else keeps the report private until a fix exists, and keeps it that way
even once the product repositories are opened up.

Please do **not** open a normal issue for a security problem. This repository's
issue tracker is public, and an issue is public from the moment it is created —
there is no way to put that back.

If GitHub advisories are unavailable to you, open a public issue that says only
that you have a security report and how to reach you privately — no details.

### What to include

The more of this you have, the faster it moves:

- The component and version — `nx-panel version`, `nx-node version`, or
  the image tag.
- What an attacker gains: read another user's subscription, take over an admin
  session, reach a node without the Panel's certificate, and so on.
- Reproduction steps, ideally the smallest ones that still work.
- Whether it needs an account, and at which role (`sudo`, `admin`, reseller,
  end-user, or none).
- Anything you already know about a fix.

Redact real subscription URLs, tokens, certificates and licence keys from
anything you attach. They are credentials.

### What happens next

- We aim to acknowledge a report within a few days, and to tell you within about
  a week whether we can reproduce it.
- You will hear about the fix before it ships, and can review it if you want to.
- The advisory is published once a fixed release is out, crediting you by
  whatever name and link you ask for — or not at all, if you prefer.

There is no bug bounty. We do not have one and would rather say so than imply
otherwise.

## Scope

**In scope** — anything that breaks one of the boundaries NX is built on:

| Boundary | What breaking it looks like |
| --- | --- |
| Admin authentication | signing in without credentials, session fixation, privilege escalation between `sudo`, `admin` and reseller |
| Reseller isolation | a reseller reading or changing users, nodes or settings that are not theirs |
| Subscription secrecy | reaching one user's subscription from another's URL, or enumerating them |
| Panel ↔ Node mTLS | driving a node without the Panel's client certificate, or a node impersonating another |
| Licence enforcement | forging a licence token, or lifting the tier limits without a valid key |
| The installers | anything that turns `install.sh` or the node installer into remote code execution against the host running it |
| Stored secrets | credentials, private keys or tokens written world-readable, logged, or exposed through the API |

Also in scope: injection, SSRF, path traversal, and anything that leaks another
operator's data in a shared deployment.

**Out of scope:**

- Findings in a third-party component that NX merely bundles — report those
  to that project directly. If the vulnerability is in *how NX uses* the
  component, or in NX's own handling around it, that is ours and we want it.
- Denial of service by sheer volume, and resource exhaustion that any operator
  could cause on their own server.
- Missing hardening headers, cookie flags or TLS options with no demonstrated
  impact. Show us what it buys an attacker.
- Self-XSS, clickjacking on pages with no state-changing action, and reports
  consisting only of a scanner's output.
- Anything requiring physical access to the Panel host or an already-root
  attacker on it. Note that the licence HWID binding is not a security boundary
  against the machine's own owner and is not treated as one.
- Social engineering of anyone in the organisation.

## Testing safely

Test against **your own** installation. Never against another operator's panel,
another operator's nodes, or any address you do not control — that is not
research, and nothing in this policy protects it.

Within your own installation, we will not pursue you for finding this in good
faith: no data destruction, no access beyond what proves the flaw, no
degradation of anyone else's service, and the details kept private until a fix
ships.

## Supported versions

The most recent release of the Panel and the most recent release of the Node.
They are versioned independently, so "latest" means each one's own latest. Fixes
land in a new release rather than being backported.
