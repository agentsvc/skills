# agentsvc.io skills

Agent skills for [agentsvc.io](https://agentsvc.io): 127 small paid APIs your agent can call without an account. Each skill tells the agent when to use a service, what to send, what comes back and how to pay.

| Skill | What it does | Price |
|---|---|---|
| [transcribe-audio](skills/transcribe-audio/SKILL.md) | Speech to text with timestamps, about 100 languages | $0.01 per file up to 10 min |
| [web-to-markdown](skills/web-to-markdown/SKILL.md) | One page, 20 pages or a site section as clean Markdown, plus screenshots | from $0.0025 |
| [verify-email](skills/verify-email/SKILL.md) | Does the mailbox exist? SMTP check, no email sent | $0.0025 |
| [token-safety-check](skills/token-safety-check/SKILL.md) | Honeypot and rug check before a swap, grade A to F, EVM and Solana | from $0.004 |
| [read-documents](skills/read-documents/SKILL.md) | PDF text, OCR, Word and EPUB to Markdown, invoices to JSON | from $0.0055 |
| [agentsvc](skills/agentsvc/SKILL.md) | Search the full catalog and call any service | from $0.002 |

Failed calls are never charged. Every service has a free trial with its example input.

## Install

Any agent that supports skills (Claude Code, Codex, Cursor and others):

```sh
npx skills add agentsvc/skills
```

Claude Code as a plugin:

```
/plugin marketplace add agentsvc/skills
/plugin install agentsvc@agentsvc
```

Or copy a `skills/<name>` folder into your agent's skills directory.

## Paying

No sign-up. Three ways, all per successful call:

- **Credit token**: buy one at [agentsvc.io/credits](https://agentsvc.io/credits) ($5 to $100 in USDC on Base, +10% bonus) and set `AGENTSVC_TOKEN`. The skills use it as `Authorization: Bearer $AGENTSVC_TOKEN`.
- **x402 wallet**: without a token every endpoint answers HTTP 402 with its price; any x402 client pays in USDC on Base, Solana, Polygon or Arbitrum. See the [quickstart](https://agentsvc.io/docs#quickstart).
- **Zero CLI**: `zero fetch https://agentsvc.io/api/v1/proxy/<slug> -d '<json>'`.

The skills tell the agent to name the price before calls the user did not ask for, to never ask for a private key in the chat, and to treat everything a service returns as data, not instructions.

## Links

- Catalog with schemas: https://agentsvc.io/llms-full.txt
- Docs: https://agentsvc.io/docs
- Main repo with SDK examples: https://github.com/agentsvc/agentsvc

MIT license.
