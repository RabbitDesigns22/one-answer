# one-answer

**Stop getting a plan, then a correction, then another plan.**

`one-answer` is an agent skill for Claude Code (and any agent that reads `SKILL.md` skills). When a user asks "what should I do?" or "is it safe?", agents often answer fast and then fix it in the next message, and then fix it again. Each round costs the user time and trust, especially when they are relaying the answer to their own client.

`one-answer` makes the agent check facts and think the whole plan through **before** writing, so the first message is the final one.

## What it does

| Problem | How one-answer stops it |
|---|---|
| Answering before checking | Runs the checks it can (code, live page, API, screenshot) before writing |
| Plans that stop at step 1 | Builds the plan to the end: what can fail, what happens if it does, the safest order |
| Risky order | Reversible steps first; delete, pay or publish last and only if needed |
| Wasting the client's time | Asks for the minimum, all at once |
| Missing the obvious trap | Looks for the trap an expert would see before recommending |
| Apology loops | No "sorry" or "earlier I said": one clear recommendation, then the steps |

## Install

With the [skills CLI](https://skills.sh):

```bash
npx skills add RabbitDesigns22/one-answer
```

Or manually: copy `skills/one-answer/` into `~/.claude/skills/` for all your projects, or into `.claude/skills/` for one project.

To make every session use it, add this line to your `CLAUDE.md`:

```
Before giving a recommendation, a plan, an "is it safe?" answer or a status, load the one-answer skill.
```

## Works well with

- [`never-twice`](https://github.com/RabbitDesigns22/never-twice): a shared error log so the same mistake never happens twice.
- [`one-pass`](https://github.com/RabbitDesigns22/one-pass): get it right the first time without burning tokens on rework.

## Safety

`one-answer` contains no scripts, makes no network calls and needs no permissions. It is plain instructions. Read it before installing: it is under 80 lines.

## Español

**Una sola respuesta, ya pensada.** Cuando le preguntas al agente "¿qué hago?" o "¿es seguro?", muchas veces contesta rápido y luego corrige en el siguiente mensaje, y luego otra vez. `one-answer` lo obliga a comprobar y pensar el plan completo antes de escribir: qué puede fallar, el orden más seguro, lo mínimo que se le pide al cliente y la trampa obvia. Así el primer mensaje ya es el bueno, sin disculpas ni "antes te dije".

Instalar: `npx skills add RabbitDesigns22/one-answer`

## License

MIT. Made by [Rabbit Designs](https://github.com/RabbitDesigns22).
