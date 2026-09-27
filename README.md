# Skills for Unicode security

Skills for Claude Code, Codex and other agents that read `SKILL.md` files, about confusables: letters that look like other letters, also called homoglyphs. A Cyrillic а in place of a Latin a is the classic example. Confusables are behind IDN homograph phishing, usernames that impersonate someone else, and text that costs an AI several times more to read.

| Plugin | Skill | Use it when |
|---|---|---|
| [namespace-guard](https://github.com/paultendo/namespace-guard/tree/main/plugins/namespace-guard) | `lookalike-names-and-text` | writing sign-up code for usernames, handles or slugs, or sending untrusted text to an LLM |
| [d0ma1n](https://github.com/paultendo/d0ma1n/tree/main/plugins/d0ma1n) | `lookalike-domains` | checking whether a domain has lookalikes registered, or reading a suspicious domain back to the one it imitates |

## Install

In Claude Code:

```bash
claude plugin marketplace add paultendo/skills
claude plugin install namespace-guard@paultendo
claude plugin install d0ma1n@paultendo
```

For Codex or another agent, copy a skill folder from the plugin links above into your agent's skills folder, such as `~/.codex/skills/`.

## What they run and contact

- **namespace-guard** runs nothing and contacts nothing. It tells the agent how to use the [namespace-guard](https://www.npmjs.com/package/namespace-guard) npm package in your project.
- **d0ma1n** has the agent call [d0ma1n.app](https://d0ma1n.app)'s API with the domain you're checking, and nothing else.

## Where the data comes from

Both use Unicode's confusables.txt (Unicode Technical Standard #39) and [confusable-vision](https://github.com/paultendo/confusable-vision), which measures 64,751 characters in 322 fonts. addons.mozilla.org checks add-on names for lookalikes with characters from confusable-vision.

The skills live in their projects' repositories, so they change with the code they describe. This repository is the catalogue.

MIT, by Paul Wood FRSA ([@paultendo](https://github.com/paultendo)).
