# one-answer

**Stop getting a plan, then a correction, then another plan.**

`one-answer` is an agent skill for Claude Code (and any agent that reads `SKILL.md` skills). When a user asks "what should I do?" or "is it safe?", agents often answer fast and then fix it in the next message, and then fix it again. Each round costs the user time and trust, especially when they are relaying the answer to their own client.

`one-answer` makes the agent check facts and think the whole plan through **before** writing, so the first message is the final one.

## See the difference

> **You:** Is it safe to move this number to the API today?

**Without the skill:** "Yes, go ahead." Next message: "Actually, first back up the chats." Then: "Sorry, one more thing..."

**With the skill:** one message: the recommendation, the trap (what you lose and when), the safe order of steps, and the minimum needed from the client, all at once.

**Skip it if** you only need a quick fact, not a decision.

**Status:** in daily use in the author's own setup. Plain instructions, no scripts, no network calls. MIT. Issues and suggestions welcome.

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

## More skills from the same setup

These come from one real workflow: a small agency run with 15+ Claude Code sessions in parallel. Each skill fixes one problem that kept happening there.

| Skill | What it fixes |
|---|---|
| [one-pass](https://github.com/RabbitDesigns22/one-pass) | get it right the first time; stop paying tokens for rework |
| [hora-exacta](https://github.com/RabbitDesigns22/hora-exacta) | real date and time in every message, so nothing lands on the wrong day |
| [hands-on](https://github.com/RabbitDesigns22/hands-on) | the agent does what it can and only asks you for codes, keys and payments |
| [easy-for-them](https://github.com/RabbitDesigns22/easy-for-them) | steps people actually follow: direct link, one action per line |
| [never-twice](https://github.com/RabbitDesigns22/never-twice) | a shared error log so no session repeats a known mistake |
| [report-now](https://github.com/RabbitDesigns22/report-now) | status checked live this minute, stamped with the time |
| [sort-me-out](https://github.com/RabbitDesigns22/sort-me-out) | one ordered list of what is urgent, waiting and forgotten |
| [in-the-loop](https://github.com/RabbitDesigns22/in-the-loop) | a live board so parallel sessions know what the others changed |
| [study-first](https://github.com/RabbitDesigns22/study-first) | reads everything in full and answers point by point, no invented details |
| [session-watchdog](https://github.com/RabbitDesigns22/session-watchdog) | wakes the sessions that got stuck mid-task, leaves the rest alone |
| [skill-harvest](https://github.com/RabbitDesigns22/skill-harvest) | reads your sessions and finds the skills you are missing |
| [small-budget-ads](https://github.com/RabbitDesigns22/small-budget-ads) | Meta Ads rules for 1-5 USD a day ad sets |
| [whatsapp-closer](https://github.com/RabbitDesigns22/whatsapp-closer) | evidence-ranked rules for a WhatsApp sales assistant that closes |
| [whatsapp-number-onboarding](https://github.com/RabbitDesigns22/whatsapp-number-onboarding) | connect a number to the WhatsApp Cloud API in the safe order |
| [proposal-pdf](https://github.com/RabbitDesigns22/proposal-pdf) | short PDF proposals with every price checked against its source |

If one of them saved you a redo, a star helps other people find it.

## License

MIT. Made by [Rabbit Designs](https://github.com/RabbitDesigns22).
