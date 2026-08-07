# GRASP

**G**enerative **R**ewriter for **A**wesomely **S**implified **P**rose.

Yes, the acronym came first. No, we are not sorry.

GRASP is an agent skill designed to help AI write like a great human writer.

The goal is simple: make AI writing feel sharper, more natural, more specific, and less like it was assembled from familiar patterns.

## What This Repo Holds

This repo is the skill. `SKILL.md` sits at the root, which means you can install it by pointing your agent straight at a clone.

- `SKILL.md`: the instructions your agent reads — a general-purpose technical explainer format built around concrete examples, step-by-step visuals, intuition-building, and clear human-sounding prose
- `evals/`: evaluation suites, a lightweight runner, and browser-ready report artifacts

The skill is named `grasp`, and it is meant to be general-purpose across technical domains: software, electronics, math, science, engineering, mechanical explainers. It is not built for softer subjects like history, philosophy, or literary analysis, where interpretation matters more than mechanism.

## Pointing Your Agent At GRASP

GRASP follows the [Agent Skills](https://agentskills.io) format, so most modern coding agents can pick it up. Installing means cloning this repo into a directory your agent already watches.

### 1. Clone it where your agent will find it

The destination folder has to be named `grasp`, since a skill's folder name must match the name declared in `SKILL.md`.

Personal install, available in every project:

| Agent | Command |
| --- | --- |
| GitHub Copilot CLI | `git clone https://github.com/kirupa/GRASP.git ~/.copilot/skills/grasp` |
| Claude Code | `git clone https://github.com/kirupa/GRASP.git ~/.claude/skills/grasp` |
| Cursor | `git clone https://github.com/kirupa/GRASP.git ~/.cursor/skills/grasp` |
| Codex CLI | `git clone https://github.com/kirupa/GRASP.git ~/.agents/skills/grasp` |

Project install, scoped to one repo and checked in for the whole team:

| Agent | Destination |
| --- | --- |
| GitHub Copilot (CLI and VS Code) | `.github/skills/grasp/` |
| Claude Code | `.claude/skills/grasp/` |
| Cursor | `.cursor/skills/grasp/` |
| Codex CLI | `.agents/skills/grasp/` |

Updating later is just a pull:

```bash
cd ~/.copilot/skills/grasp && git pull
```

If you already have a clone somewhere you like, symlink it instead of cloning twice:

```bash
mkdir -p ~/.copilot/skills
ln -s /path/to/GRASP ~/.copilot/skills/grasp
```

### 2. Ask for writing, and let the skill do its thing

Agents load a skill on their own when your request matches its description, so this is usually enough:

> Write a blog post explaining how DNS resolution actually works.

If you want to be sure it fired, name it directly:

> Use the grasp skill to explain how DNS resolution actually works.

Copilot CLI can confirm the agent sees it. Run these inside a Copilot CLI session:

```text
/skills list
/skills info grasp
```

If you edit the skill mid-session, `/skills reload` picks up the change without a restart.

### 3. Know when not to use it

`grasp` is tuned for explainers: tutorials, guides, posts that build intuition before getting formal. Point it at a changelog or an API reference and you will get a friendly, chatty changelog, which is nobody's goal.

## Running Evals

The default eval command is:

```bash
ruby evals/run_evals.rb run grasp
```

That creates both of these files by default:

- `evals/reports/grasp-YYYY-MM-DD.json`
- `evals/reports/grasp-YYYY-MM-DD.html`

The JSON file is the source of truth. The HTML file is the rendered report you can open directly in a browser.

## Direction

GRASP is for writing that sounds like a person with taste, judgment, and a point of view.

That usually means:

- less filler
- fewer canned transitions
- more specificity
- better rhythm
- clearer technical explanation
- stronger voice without losing accuracy
