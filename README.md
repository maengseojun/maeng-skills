# maeng: Claude Code skills and agents

Skills and agents from my personal Claude Code harness: the craft skills I use every day to research, write, design and ship code with AI agents.

This repository is a curated export. My working harness lives in a private repository; what is here is the part that works without my accounts, notes and gates.

## Install

In Claude Code:

```
/plugin marketplace add maengseojun/maeng-skills
/plugin install maeng-tools@maeng
/plugin install maeng-harness@maeng
```

Or copy a single skill folder (`plugins/*/skills/<name>/`) into `~/.claude/skills/`. Each skill is one folder with a `SKILL.md`.

## What is in it

| Plugin | What it holds |
| --- | --- |
| [`maeng-tools`](plugins/maeng-tools) | 24 hookless craft skills and 7 model-routed agents. Safe in any repository. |
| [`maeng-harness`](plugins/maeng-harness) | 7 engineering skills from the harness: optimization proofs, debugging, prototypes and handoff. The hooks and gate CLIs stay private. |

### Agents

Each agent pins a model to a role, so work goes to the cheapest model that can do it well:

- `architect` and `design` run on Opus. They handle design and planning.
- `implementer`, `standard` and `design-reviewer` run on Sonnet. They implement, verify and review rendered UI.
- `researcher` and `quick` run on Haiku. They do reading and exact small edits.

### Skills

**Research and writing**
- `coherent-writing`, `personal-essay`, `manuscript-writing-review`: connected prose in Korean and English.
- `easy-understanding`: explains a concept or a decision from first principles, with a map of what the reader must decide.
- `prepare-work-deliverable`: turns an agreed brief into a report, pitch or deck with connected evidence.
- `ai-loop-design`: a checklist for splitting an AI product between the model, code and the human, with verification criteria fixed before generation.
- `blockchain-upstream-review`: reads upstream commits and PRs against a project's actual dependency pins and call sites.

**Visuals and video**
- `diagram-explainer`: about 45 diagram and chart types as branded HTML, SVG and PNG.
- `interactive-explainer`: explorable explanations where changing a value teaches something.
- `frontend-slides`, `presentation-design-interview`: web slide decks and interview-led slide design.
- `motion-studio`, `tutorial-video`: short product videos and narrated lessons, made in code.

**Front-end**
- `frontend-guidance`, `cinematic-site`, `design-reference`, `html-prototype-interview`: visual direction from real references, landing pages, and prototypes the user explores while being interviewed.
- `hangul-wrap`: measures Korean line breaks in a real browser and fixes words split in half.

**Code**
- `proof-guided-optimization`: justifies algorithms and DeFi math with proofs, bounds and explicit tradeoffs.
- `error-fix-manual-1`: traces a recurring save, sync or readback failure from the raw response and fixes it at the source.
- `gh-fix-ci`, `gh-address-comments`: fix failing GitHub checks and work through review comments with `gh`.

**Agents and tools**
- `task-brief`: turns a large assignment into a handoff brief for another agent.
- `ask-claude`: delegates a task or asks for a second opinion through `claude -p`.
- `orca-race`: has Claude and Codex attack an unclear bug separately, then compares.
- `skill-feedback`: turns a reusable correction into a revision of the skill that caused it.
- `notion-authoring`: builds and verifies Notion documents, databases and views.
- `aside-browser`, `playwright`, `screenshot`: browser and screen automation.
- `vercel-deploy`: deploys a site or app to Vercel.

## How my private harness works

The skills above come from a larger loop that stays private because it is wired to my own Linear, Notion and Obsidian:

1. **Plan.** A large request becomes an interview, a Spec and Plan with acceptance criteria, and a task tree.
2. **Route.** Each task goes to the agent and model that fit it.
3. **Verify.** A verifier checks the result against the exact working tree it was built on, and an independent reviewer model reads the diff.
4. **Understand.** Before code moves on, I have to explain and defend the design without AI help. A short quiz built from running the code gates large merges. Agent recommendations are sealed before I choose, so my choice cannot tilt them.
5. **Ship.** Hooks block a direct push to the default branch. Merges go through a ship CLI after review and checks pass.
6. **Record.** Outcomes are written to my notes, and reusable corrections become skill revisions.

## License

[MIT](LICENSE) for my own work. Some skills adapt open-source work. Their sources are named in each skill, and their licenses sit next to them or in [`plugins/maeng-tools/licenses`](plugins/maeng-tools/licenses).

This is a personal repository. You are welcome to fork it and adapt any skill.
