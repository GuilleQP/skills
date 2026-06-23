---
name: gitmoji
description: Generate a git commit message prefixed with the single most fitting Gitmoji, following the gitmoji.dev convention. Use ONLY when the user explicitly asks for a commit message that uses gitmoji — e.g. "write a gitmoji commit", "commit this with gitmoji", "gitmoji commit message", "add an emoji to my commit". Picks the right emoji for the change, writes a concise imperative subject, and follows the `<emoji> <subject>` format. Not for plain (non-emoji) commit messages.
---

# Gitmoji commit messages

Produce a commit message that starts with one [Gitmoji](https://gitmoji.dev) — an emoji that signals the *intent* of the change at a glance. Only use this skill when the user has explicitly asked for a gitmoji / emoji commit message.

## Format

```
<emoji> <subject>

[optional body]
```

Rules:

1. **Exactly one emoji**, at the very start, followed by a single space. Use the rendered emoji (`✨`), not the code (`:sparkles:`), unless the user's tooling needs the code (e.g. a `commitlint`/`gitmoji-cli` setup) — then ask or match what their repo already uses.
2. **Subject:** imperative mood, lowercase after the emoji unless a proper noun, no trailing period, aim for ≤ 50 characters.
3. **Body (optional):** add only if the change needs explanation — wrap at ~72 chars, explain *what* and *why*, not *how*.
4. An optional scope is allowed: `✨ (auth) add password reset`.

## Method

1. **Identify the dominant intent** of the change. A commit should do one thing; pick the emoji for that one thing. If staged changes truly span two intents, prefer the most significant — or suggest splitting the commit.
2. **Map intent → emoji** using the table below for common cases, or [`references/gitmojis.md`](references/gitmojis.md) for the full list of all gitmojis.
3. **Write the subject** describing the change concisely in the imperative ("add", "fix", "remove" — not "added"/"fixes").
4. If you can inspect the diff (e.g. `git diff --staged`), base the emoji and subject on what actually changed rather than guessing.

## Most common gitmojis

| Emoji | Code | When |
|-------|------|------|
| ✨ | `:sparkles:` | Introduce new features |
| 🐛 | `:bug:` | Fix a bug |
| 🚑️ | `:ambulance:` | Critical hotfix |
| ♻️ | `:recycle:` | Refactor code |
| ⚡️ | `:zap:` | Improve performance |
| 🔥 | `:fire:` | Remove code or files |
| 📝 | `:memo:` | Add or update documentation |
| 💄 | `:lipstick:` | UI / style changes |
| ✅ | `:white_check_mark:` | Add, update, or pass tests |
| 🔧 | `:wrench:` | Add or update config files |
| ⬆️ | `:arrow_up:` | Upgrade dependencies |
| ⬇️ | `:arrow_down:` | Downgrade dependencies |
| ➕ | `:heavy_plus_sign:` | Add a dependency |
| ➖ | `:heavy_minus_sign:` | Remove a dependency |
| 🚨 | `:rotating_light:` | Fix compiler / linter warnings |
| 🔒️ | `:lock:` | Fix security or privacy issues |
| 🚀 | `:rocket:` | Deploy stuff |
| 🎉 | `:tada:` | Begin a project |
| 🔖 | `:bookmark:` | Release / version tags |
| 🚧 | `:construction:` | Work in progress |
| ✏️ | `:pencil2:` | Fix typos |
| 🏷️ | `:label:` | Add or update types |
| 👷 | `:construction_worker:` | Add or update CI build system |
| 💚 | `:green_heart:` | Fix CI build |
| ⏪️ | `:rewind:` | Revert changes |
| 🚚 | `:truck:` | Move or rename resources |
| 💥 | `:boom:` | Introduce breaking changes |

For anything not covered here, consult [`references/gitmojis.md`](references/gitmojis.md).

## Examples

> 🐛 fix off-by-one error in pagination offset

> ✨ (api) add endpoint for exporting reports as CSV

> ♻️ extract validation logic into reusable hook

> 📝 document environment variables in README

A fuller example with a body:

```
🔒️ patch XSS in comment rendering

User-supplied comment HTML was injected unescaped. Sanitize on
render and add a regression test covering script tags.
```

## Output

Return the commit message ready to use. If the user wants to commit directly and you can run commands, you may offer:

```
git commit -m "✨ add dark mode toggle"
```

Keep it to the single message unless the user asks for alternatives. If the change is ambiguous, briefly state which emoji you chose and why, or offer the top two candidates.
