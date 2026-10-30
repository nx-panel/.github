# Contributing

Thanks for wanting to help. Read this first, because NX is shaped unusually:
**the Panel and Node source is not public**, so most contributions arrive as
issues rather than as pull requests.

## Where things go

| | Where |
| --- | --- |
| Bug reports and feature requests | The issues of [`panel`](https://github.com/nx-panel/panel/issues/new/choose), or of [`node`](https://github.com/nx-panel/node/issues/new/choose) for a problem only on a node |
| Questions about using NX | [SUPPORT.md](SUPPORT.md) |
| Security vulnerabilities | [A private advisory](https://github.com/nx-panel/.github/security/advisories/new) — never an issue. See [SECURITY.md](SECURITY.md) |
| Fixes to the organisation files here | A pull request on this repository |

Pull requests against the Panel or the Node cannot be accepted, because their
source is not public. That is not a judgement on the patch. If
you have written a fix, describe it in an issue — a clear description of the
cause and the change is genuinely useful, and it gets credited when it ships.

## Reporting a bug

Use the **Bug report** form. It asks for the versions, the install method and the
logs because those three answer most questions before they are asked.

A few things worth more than anything else you can write:

- **Reproduction steps that start from a fresh install.** If a bug only appears
  on your configuration, say what is unusual about it.
- **Which side it happens on.** Panel and Node fail in very different ways, and
  the same symptom ("users cannot connect") has causes in both.
- **Whether it survives a restart**, and whether it survives a full resync from
  the panel.

One problem per issue. Two problems in one thread means one of them gets lost.

## Requesting a feature

Use the **Feature request** form, and lead with the problem rather than the
solution. "I run three panels for different customers and cannot tell their
traffic apart" is something that can be designed for; "add a dropdown here" is
already a design, and often not the one that fits.

Requests to support another protocol are welcome, but the size of the job varies
enormously. Surfacing a protocol the Node's engine already speaks is a small
change; one it does not speak at all is a different project. Say which protocol
and which clients you need to reach, and we will say which of the two it is.

## Translations

The Panel's admin UI and the installation guides are in English, Persian,
Chinese and Russian. Corrections and additions to any of them are among the most
useful things an outside contributor can send, and they do not need access to the
source: open an issue with the strings or the passage as it should read, and say
which language and which screen or page it belongs to.

## Pull requests on this repository

Only the organisation files live here, but the same conventions apply as
everywhere else in NX:

- Commit subjects are lowercase and use an area prefix where one fits —
  `docs:`, `ci:`, `security:`. Say what changed, not that something changed.
- Explain **why** in the body. What the diff does is already in the diff.
- One concern per pull request.
- Match the wrapping of the file you are editing. Reflowing a whole paragraph
  to change one word buries the change in the diff.
- Fill in the pull request template. It is short on purpose.

## What happens to your report

Issues are triaged by hand. Expect a real answer rather than a fast one — a
report with versions, logs and steps usually gets one within a few days; one
without them usually gets a request for them instead. Issues that go quiet
waiting on information are closed, and reopening them with the information is
welcome at any time.
