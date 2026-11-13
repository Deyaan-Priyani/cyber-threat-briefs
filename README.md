# Cyber Threat Briefs

Short, student-level write-ups explaining recent cybersecurity events: what
happened, why it matters, and what defenders can learn.

Prepared with AI assistance for research, drafting and editing. Sources are
linked beside the claims they support. These are public-source research briefs,
not investigations of systems I accessed.

## Briefs

| Event | Type | Main lesson |
| --- | --- | --- |
| [PHP2Shell](briefs/2026-10-php2shell.md) | Exploitation of PHP software vulnerabilities | Patch exposed services and verify actual compromise. |
| [Grocery and cold-chain refrigeration attacks](briefs/2026-11-cold-chain-refrigeration.md) | Attacks on operational technology | Internet access to physical controls creates business and safety risks. |
| [Bank of America and third-party AI agents](briefs/2026-10-bofa-ai-agent-access.md) | AI-agent access and credential-risk event | Understand permissions before connecting an agent to financial accounts. |

The Bank of America brief covers an access-risk warning and related industry
reporting. The reviewed sources do not establish a Bank of America breach.

## Method

1. Start with a vendor advisory, government notice or original research.
2. Check dates and distinguish vulnerabilities, attempts and confirmed effects.
3. Write 300–500 words using the [incident template](templates/incident-template.md).
4. Add a small [MITRE ATT&CK](https://attack.mitre.org/) table where the behavior fits.
5. Separate reported facts from my analysis and recommendations.

Severity descriptions are my assessment unless an official score is identified.
ATT&CK mappings are my interpretation, not an official MITRE assessment of these
events. Each brief records its review date because reporting can change.

## Folder guide

- `briefs/`: the three write-ups.
- `templates/`: a format to reuse for future events.
- `resources/glossary.md`: short definitions of key terms.

**Last reviewed:** November 13, 2026.
