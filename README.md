# Dreyfus Method

A plugin that makes Claude a better teacher. It applies the Dreyfus model of skill acquisition and Fernando Flores and Terry Winograd's ideas about language and learning whenever Claude teaches or explains something.

Without it, Claude tends to explain a concept by describing what it *is*. With it, Claude:

- **Gauges your level.** Beginners get clear rules. People with more experience get tradeoffs, and experts get a conversation between peers.
- **Starts from a problem you already have.** It introduces a new idea through the problem it solves for you, before any new terms.
- **Explains each term by what it lets you do.** "You'd reach for this when..." instead of "X is defined as..."
- **Builds one idea on the last.** It makes sure the first idea is solid before adding the next, and uses words you already know.

## Example

Asked "Teach me about markdown files and how they compare to HTML, JSON, or TXT", Claude without the skill gave an accurate description of each format, with a different example for each one ("JSON is a data interchange format: structured key-value pairs for machines to parse").

With an earlier version of this skill, Claude framed each format around when you would reach for it. It wrote the same shopping list in all four formats so the differences were easy to see, and ended with a rule you can reuse:

> **TXT and Markdown** are for content humans write and read.
> **HTML** is for content humans read but browsers render.
> **JSON** is for data programs read and write.

## How to use it

The skill switches on by itself when you ask Claude to explain or teach something, or when you keep asking about the same term. In Claude Code you can also call it directly:

```
/dreyfus how OAuth works
```

## Install

**Claude Code**, from this repository:

```
/plugin marketplace add kumarshyam42/dreyfus
/plugin install dreyfus-method@kumarshyam42
```

**claude.ai and the Claude desktop app:** download this repository as a zip, then go to **Customize > Plugins > Add > Upload plugin**.

## What it runs and sends

Nothing. The plugin is a single instruction file (`skills/dreyfus/SKILL.md`). It contains no scripts or hooks, connects to no servers, and sends no data anywhere.

## Background

- The [Dreyfus model of skill acquisition](https://en.wikipedia.org/wiki/Dreyfus_model_of_skill_acquisition) describes how people move from novice to expert, and why each stage needs different teaching.
- Fernando Flores and Terry Winograd treat knowing as effective action rather than holding accurate descriptions. In their view, every domain exists to deal with recurring breakdowns, the moments when something we need is missing.

## License

MIT
