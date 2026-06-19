# no-bullshit

A Claude skill that switches Claude into a direct, no-filler answering mode: lead with the answer, cut preamble and postamble, drop hedging and filler, no flattery.

It's for people who'd rather read two honest sentences than four padded paragraphs — and who'd like to save tokens while they're at it.

## What it does

When you signal you want a blunt answer ("no bs", "be direct", "cut the fluff", "/no-bullshit", etc.), Claude:

1. **Leads with the answer** — conclusion first, reasoning after.
2. **Cuts preamble/postamble** — no "Great question!", no closing recap.
3. **Drops hedging and filler** — commits to a position; names *real* uncertainty only.
4. **Skips flattery** — no automatic compliments.

It stays in this mode for the rest of the conversation until you say otherwise. It deliberately does *not* cut real substance, necessary caveats, or safety warnings — it cuts padding, not information.

## Install

A skill is just a folder containing a `SKILL.md`. Drop the `no-bullshit/` folder into your skills directory:

**Claude Code / Cowork**
```
~/.claude/skills/no-bullshit/
```

So the final path looks like `~/.claude/skills/no-bullshit/SKILL.md`.

On Windows that's typically:
```
%USERPROFILE%\.claude\skills\no-bullshit\
```

Then start (or restart) your session. To install via clone:

```bash
git clone https://github.com/andrejbosnjakk/no-bullshit-claude.git
cp -r no-bullshit-claude/no-bullshit ~/.claude/skills/
```

## Use

Just ask for it in natural language:

> no bs — should I use Postgres or Mongo for this?

> be direct, is this regex correct?

> /no-bullshit

Claude will load the skill and answer straight, then keep answering straight for the rest of the chat. Tell it "back to normal" to turn it off.

## How it works

The whole skill is one Markdown file, [`no-bullshit/SKILL.md`](no-bullshit/SKILL.md). The YAML `description` at the top is what Claude scans to decide when to load the skill; the body is the instructions it follows once loaded. Edit either to taste.

## License

MIT — see [LICENSE](LICENSE).
