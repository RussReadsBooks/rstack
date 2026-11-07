# rstack

Russell Newman's small, growing set of agent skills and standing rules for Claude Code and Cursor. Each one captures a habit I'd like my agents to have by default, so I don't have to explain it every session.

Inspired by [pstack](https://github.com/cursor/plugins/tree/main/pstack) and [Matt Pocock's skills](https://github.com/mattpocock/skills).

## Skills

| Skill                                                                  | What it does                                                                                                                                                                                                                                        |
| ---------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [how-to-ask-good-questions](skills/how-to-ask-good-questions/SKILL.md) | Decide the small stuff yourself. When a real decision needs the user, package every open question into one message with numbered questions, lettered options, the data needed to choose, and an inline recommendation. The user replies `1A 2B 3A`. |

## Standing rules

[`AGENTS.md`](AGENTS.md) holds the always-on rules (`CLAUDE.md` is a symlink to it):

- **Voice transcription.** Treat odd words as speech-to-text errors, state the assumed meaning once, and keep going.
- **Unslop.** Run every piece of prose through pstack's `/unslop` before sending it.
- **How to ask questions.** Points at the skill above.

## Install

**Claude Code**

```
/plugin marketplace add RussReadsBooks/rstack
/plugin install rstack@rstack
```

**Cursor:** the repo includes a `.cursor-plugin/plugin.json`. Until rstack is listed on the Cursor marketplace, [install it as a local plugin](https://cursor.com/docs/plugins), or copy the `skills/` folders into `~/.cursor/skills/`.

**Anything else:** each skill is a plain `SKILL.md` in the [Agent Skills](https://agentskills.io) format, so you can copy it wherever your agent reads skills.


## License

[MIT](LICENSE)
