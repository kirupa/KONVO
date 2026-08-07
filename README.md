# GRASP

**G**enerative **R**ewriter for **A**wesomely **S**implified **P**rose.

Yes, the acronym came first. No, we are not sorry.

GRASP is a collection of agent skills designed to help AI write like a great human writer.

The goal is simple: make AI writing feel sharper, more natural, more specific, and less like it was assembled from familiar patterns.

## What This Repo Holds

Each folder in this repository represents a writing-focused skill, playbook, or style system.

The first collection area is:

- `technical-casual`: skills for explaining technical ideas in a relaxed, clear, human way

## Structure

Each skill should typically include:

- `SKILL.md`: the main instructions for the agent
- supporting references, examples, or notes as needed

The repo also includes:

- `evals/`: evaluation suites, a lightweight runner, and browser-ready report artifacts

## Pointing Your Agent At GRASP

GRASP skills follow the [Agent Skills](https://agentskills.io) format, so most modern coding agents can pick them up. Installing one means putting the skill folder somewhere your agent already looks.

### 1. Grab the repo

```bash
git clone https://github.com/kirupa/GRASP.git
cd GRASP
```

### 2. Drop the skill where your agent will find it

Personal install, available in every project:

| Agent | Destination |
| --- | --- |
| GitHub Copilot CLI | `~/.copilot/skills/technical-casual/` |
| Claude Code | `~/.claude/skills/technical-casual/` |
| Cursor | `~/.cursor/skills/technical-casual/` |
| Codex CLI | `~/.agents/skills/technical-casual/` |

Project install, scoped to one repo and checked in for the whole team:

| Agent | Destination |
| --- | --- |
| GitHub Copilot (CLI and VS Code) | `.github/skills/technical-casual/` |
| Claude Code | `.claude/skills/technical-casual/` |
| Cursor | `.cursor/skills/technical-casual/` |
| Codex CLI | `.agents/skills/technical-casual/` |

Copying works:

```bash
mkdir -p ~/.copilot/skills
cp -R technical-casual ~/.copilot/skills/
```

Symlinking works better, because a later `git pull` updates the skill in place:

```bash
mkdir -p ~/.copilot/skills
ln -s "$(pwd)/technical-casual" ~/.copilot/skills/technical-casual
```

### 3. Ask for writing, and let the skill do its thing

Agents load a skill on their own when your request matches its description, so this is usually enough:

> Write a blog post explaining how DNS resolution actually works.

If you want to be sure it fired, name it directly:

> Use the technical-casual skill to explain how DNS resolution actually works.

Copilot CLI can confirm the agent sees it. Run these inside a Copilot CLI session:

```text
/skills list
/skills info technical-casual
```

If you edit a skill mid-session, `/skills reload` picks up the change without a restart.

### 4. Know when not to use it

`technical-casual` is tuned for explainers: tutorials, guides, posts that build intuition before getting formal. Point it at a changelog or an API reference and you will get a friendly, chatty changelog, which is nobody's goal.

## Running Evals

The default eval command is:

```bash
ruby evals/run_evals.rb run technical-casual
```

That creates both of these files by default:

- `evals/reports/technical-casual-YYYY-MM-DD.json`
- `evals/reports/technical-casual-YYYY-MM-DD.html`

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
