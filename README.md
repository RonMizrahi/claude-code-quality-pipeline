# Ron Mizrahi's Claude Code Plugins

A **public [Claude Code](https://code.claude.com) plugin marketplace** by
**[Ron Mizrahi](https://github.com/RonMizrahi)** — practical engineering workflows, packaged as
plugins, free for everyone to install and use.

Marketplace name: **`ron-mizrahi`**

## Install

```
/plugin marketplace add RonMizrahi/claude-plugins
/plugin install code-quality-pipeline@ron-mizrahi
```

Then run `/plugin` to browse everything published here.

## Plugins

| Plugin | Skill | What it covers |
|---|---|---|
| **[code-quality-pipeline](plugins/code-quality-pipeline)** | `code-quality-pipeline` | The quality gates between "code written" and "code merged": a 4-step per-file review pipeline (Code Review → Simplification → Security → Final) plus a holistic pre-merge diff review. |

More plugins coming — this marketplace grows one battle-tested workflow at a time.

## Layout

```
.claude-plugin/marketplace.json      # marketplace manifest (name: ron-mizrahi)
plugins/<plugin>/
├── .claude-plugin/plugin.json        # per-plugin manifest
├── README.md                         # what the plugin is
└── skills/<skill>/SKILL.md           # the skill itself
LICENSE                               # MIT
```

## License

MIT © Ron Mizrahi. See [`LICENSE`](LICENSE).
