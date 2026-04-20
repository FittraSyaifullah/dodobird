# dodobird
Dodobird, ultrathin token-reduction layer for AI coding tools.

dodobird 🐦

Ultrathin token compression for AI coding agents.

Fewer tokens. Same meaning. Always.
dodobird installs a compression skill into Cursor, Claude Code, and Codex CLI that strips filler, preamble, and redundancy from every AI response — without losing accuracy or meaning.

Install
bash# Global install (recommended)
npm install -g dodobird

# Or run directly without installing
npx dodobird install
One-liner (no npm required):
bashcurl -fsSL https://raw.githubusercontent.com/yourusername/dodobird/main/install.sh | sh

Usage
bashdodobird install           # install to all detected tools
dodobird install cursor    # Cursor only
dodobird install claude    # Claude Code only
dodobird install codex     # Codex CLI only
dodobird list              # show install status

What it does
Before dodobird:
Sure! Happy to help with that. So what you're asking is how to fix 
the auth middleware. Let me walk you through the solution step by step. 
Here's the updated function. I've added a try/catch block to handle 
errors gracefully...

[code]

Hope that helps! Let me know if you have any questions!
After dodobird:
[code]

What gets cut
PatternExampleActionOpening filler"Sure! Happy to help."DeletedRestatement"So what you're asking is..."DeletedHedging"It's worth noting that..."→ "Note:"Connector bloat"In order to", "Basically"DeletedOver-explanation3 sentences about a 1-line change→ 0–1 sentencesClosing filler"Let me know if you need anything!"Deleted
What never gets cut

Correctness
Security / breaking-change warnings
Code that must be complete to run
Clarifying questions when the task is ambiguous


Philosophy
The dodo: famously extinct, zero fat, pure form.
dodobird is not a summarizer. It doesn't cut meaning — it cuts the packaging around meaning. The goal is precision density: maximum signal per token.
In AI coding tools, token count is a proxy for cost, latency, and cognitive load. Most AI outputs are 30–60% filler. dodobird eliminates that without touching the 40–70% that matters.

How it works
dodobird installs a SKILL.md file into each tool's configuration directory:
ToolLocationCursor~/.cursor/rules/dodobird.mdc or .cursor/rules/dodobird.mdcClaude Code~/.claude/skills/DODOBIRD.md or .claude/DODOBIRD.mdCodex CLI~/.codex/instructions/dodobird.md or .codex/dodobird.md
The skill file contains compression rules, antipattern catalogs, and per-tool guidance that the AI agent loads into context on every session.

Contributing
Open source, MIT. PRs welcome.
dodobird/
├── bin/dodobird.js         CLI
├── skill/
│   ├── SKILL.md            Core compression rules
│   └── references/
│       ├── antipatterns.md Full pattern catalog
│       └── mode-guides.md  Per-tool guidance
├── package.json
└── README.md

License
MIT
