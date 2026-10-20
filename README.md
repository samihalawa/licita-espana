# Licita España

Turn a Spanish public tender into a traceable opportunity brief and a clause-by-clause qualification checklist.

**Author:** Sami Halawa · **Version:** 0.1.2 · **Format:** portable skills plugin + Claude plugin manifest · **Code licence:** MIT.

## What is included

A dedicated workflow, official source references, self-contained Python 3.11+ adapters, icon, support/data-practices documents and acceptance examples. It is not an already hosted MCP app or an approved public-directory listing.

## Install in Claude Code

```bash
claude plugin marketplace add samihalawa/licita-espana
claude plugin install licita-espana@licita-espana
```

Inside a Claude Code session (v2.1.275+), the one-step equivalent is:

```text
/plugin install licita-espana --marketplace samihalawa/licita-espana
```

The adapter requires Python 3.11+ and access to its official data providers. No separate product account, API key, payment or publisher-hosted service is required. A host that cannot execute Python may use the workflow with its available native browsing and supplied documents. The package does not grant unavailable host permissions or network access.

## Use

Ask: “Find recent Spanish software tenders and show exactly what was searched.”

In ChatGPT, the workflow uses native browsing or your supplied documents. Local Python networking is not assumed. In Claude Code/Codex, use `skills/licita-espana/scripts/run.py` to retrieve official public data.

```bash
python3 skills/licita-espana/scripts/run.py list
python3 skills/licita-espana/scripts/run.py call licita_search --json '{"query": "software", "max_pages": 1, "limit": 10}'
```

## Limits

No exhaustive historical procurement index, private portal automation, digital signatures, bid submission, legal opinions or unattended monitoring. The parser returns document URLs; the host must read the actual documents before qualification.

No source credentials, paid API calls, subscriptions, account database or publisher telemetry are bundled. No background jobs are started.

## Public source and submission

This repository is the complete standalone source. [Claude submission information](SUBMISSION.md), [privacy](PRIVACY.md), [terms](TERMS.md), [support](SUPPORT.md) and [security](SECURITY.md) are included.

This is an independent skills plugin by Sami Halawa, not an official government service or an approved Anthropic directory listing. Public repository publication, successful installation and directory approval are separate states.

## Development verification

Run `python3 scripts/check_package.py` and `claude plugin validate --strict .claude-plugin/plugin.json`. An optional GitHub Actions template is provided at `ci/validate.yml`. It is not active: the publishing credential has repository access but no workflow-write permission. Installation is verified directly in a fresh Claude configuration. These checks do not establish model-based user acceptance or continued availability of government services. See `evidence/claude-validation.json` and `evidence/live-probes.json` for the exact observed state; a CI template is not a completed CI run.
