# ✍️ KONVO

**K**ill
**O**bscurity with
**N**arrative,
**V**isuals, and
**O**nramps.

Yes, the acronym came first. No, we are not sorry.

**KONVO is not about helping AI write. It is about helping you write, with AI doing the tedious parts.**

You are the author. The piece goes out under your name, gets read by people who trust you, and reflects your judgment about what actually matters. KONVO keeps the agent working to your standard instead of its own, so what comes back is closer to the article you would have written yourself if you'd had a free Saturday.

That distinction does real work. An agent left alone writes something fluent, agreeable, and forgettable. It doesn't know who your reader is, what they already know, or which part of the topic is the one everybody gets stuck on. You know all of that. KONVO is the structure that pulls it out of your head and into the draft, then handles the parts you don't want to do by hand: the scaffolding, the worked example, the fourth rewrite of a paragraph that still isn't landing.

The point is more good technical writing in the world, published by the people who understand the material.

## 🤝 How the Work Splits

KONVO assumes you know things the agent never will, and it is built to go get them.

Before it writes a new long-form piece, the skill interviews you. What is the topic, who is the reader, what should they be able to do afterward, what kind of content are you making, how long should it run, and should images be placeholder markers or real generated visuals. It asks rather than guessing, because guessing is how you end up with a competent article about something adjacent to what you meant.

**You bring** the reason this is worth writing, the reader you have in mind, the place people reliably get stuck, the opinion you are willing to defend, and the real numbers and war stories that make it yours.

**The agent brings** the draft, the structure, the worked example, the diagram placement, and unlimited patience for the fifth pass on a section you have stopped being able to see clearly.

**KONVO brings** the standard, so you are not re-explaining your taste at the start of every session.

There is a chunk of the skill devoted to stripping the tells that make writing read as machine-generated. That is not about sneaking anything past anyone. It is because you are the one whose name is on it, and a reader who smells autopilot stops trusting the explanation, even when the explanation is correct.

## 🧒 From ELI5 to Deep Dive

Tell KONVO who the reader is. It can explain the same technical idea to a curious five-year-old, a newcomer, or somebody who has worked in the field for decades.

KONVO adjusts vocabulary, examples, sentence length, pacing, assumed knowledge, visuals, code, math, and implementation detail. It simplifies the route into a topic without changing the underlying facts. Age and expertise are separate, so give it either the reader's age, what they already know, or both.

For a true ELI5 explanation:

> Use the KONVO skill to explain DNS resolution to a curious five-year-old. Keep it concrete, accurate, short, and visual. Use familiar examples and define any technical word you cannot avoid.

For a deep-dive primer:

> Use the KONVO skill to explain DNS resolution to experienced network engineers. Skip the basics they already know and focus on caching layers, failure modes, delegation, DNSSEC, and operational debugging.

## 📚 Where This Comes From

KONVO is not a writing style somebody guessed at over a weekend. It is distilled from about 30 years of [Kirupa](https://www.kirupa.com)'s published writing, which turns out to be a genuinely unreasonable amount of material:

- roughly 1,700 [articles and tutorials](https://www.kirupa.com/learn/index.htm)
- 9 [published books](https://www.kirupa.com/book/index.htm)
- around 15,000 [forum posts](https://forum.kirupa.com)
- thousands of emails, which are staying right where they are, thanks

That is three decades of explaining technical things to people who did not understand them yet, then finding out in real time whether the explanation landed. Forum posts are especially good teachers here, because a confused reply is instant, unambiguous feedback that your explanation did not work.

The point was never to clone one person's voice. It was to find the moves that kept working across all that material, then write them down so they can serve yours.

## 📦 What This Repo Holds

This repo is the skill. `SKILL.md` sits at the root, which means you can install it by pointing your agent straight at a clone.

- `SKILL.md`: the instructions your agent reads, which lay out a general-purpose technical explainer format built around concrete examples, step-by-step visuals, intuition-building, and clear human-sounding prose
- `evals/`: evaluation suites, a lightweight runner, and browser-ready report artifacts

The skill is named `konvo`, and it is meant to be general-purpose across technical domains: software, electronics, math, science, engineering, mechanical explainers. It is not built for softer subjects like history, philosophy, or literary analysis, where interpretation matters more than mechanism.

## 🎯 Pointing Your Agent At KONVO

KONVO follows the [Agent Skills](https://agentskills.io) format, so most modern coding agents can pick it up. Installing means cloning this repo into a directory your agent already watches.

### 1. 📥 Clone it where your agent will find it

The destination folder has to be named `konvo`, since a skill's folder name must match the name declared in `SKILL.md`.

Personal install, available in every project:

| Agent | Command |
| --- | --- |
| GitHub Copilot CLI | `git clone https://github.com/kirupa/KONVO.git ~/.copilot/skills/konvo` |
| Claude Code | `git clone https://github.com/kirupa/KONVO.git ~/.claude/skills/konvo` |
| Cursor | `git clone https://github.com/kirupa/KONVO.git ~/.cursor/skills/konvo` |
| Codex CLI | `git clone https://github.com/kirupa/KONVO.git ~/.agents/skills/konvo` |

Project install, scoped to one repo and checked in for the whole team:

| Agent | Destination |
| --- | --- |
| GitHub Copilot (CLI and VS Code) | `.github/skills/konvo/` |
| Claude Code | `.claude/skills/konvo/` |
| Cursor | `.cursor/skills/konvo/` |
| Codex CLI | `.agents/skills/konvo/` |

Updating later is just a pull:

```bash
cd ~/.copilot/skills/konvo && git pull
```

If you already have a clone somewhere you like, symlink it instead of cloning twice:

```bash
mkdir -p ~/.copilot/skills
ln -s /path/to/KONVO ~/.copilot/skills/konvo
```

### 2. 💬 Ask for writing, and expect questions back

Agents load a skill on their own when your request matches its description, so this is usually enough:

> Write a blog post explaining how DNS resolution actually works.

If you want to be sure it fired, name it directly:

> Use the KONVO skill to explain how DNS resolution actually works.

Either way, the first thing back is usually not a draft. It is a short set of questions about topic, audience and depth, goal, content type or channel, target length, and images. Those two minutes pay for themselves, because everything downstream is built on your answers. You can front-load them instead:

> Use the KONVO skill to write a 1,200-word article explaining how DNS resolution works, aimed at bootcamp grads who have never thought about where an IP address comes from. The goal is for them to trace a lookup and identify where it failed. The thing they usually get wrong is assuming the browser talks to one server. Placeholder image markers are fine.

For the fewest rewrites, provide the fields explicitly:

```text
Use the KONVO skill to help me create or improve the content below.

Topic: [WHAT IS THIS ABOUT?]
Target reader: [AGE / EXPERIENCE LEVEL / PRIOR KNOWLEDGE]
Goal: [WHAT SHOULD THE READER UNDERSTAND OR DO?]
Content type / channel: [ARTICLE / X POST / EMAIL RESPONSE / ETC.]
Target length: [WORDS / CHARACTERS / READING TIME / NUMBER OF POSTS]
Visuals: [PLACEHOLDERS / GENERATED / NONE]
Additional notes: [TONE / MUST-INCLUDE / MUST-AVOID / SOURCES]

[PASTE YOUR DRAFT, NOTES, OR SOURCE MATERIAL HERE]
```

Content type and target length are separate on purpose. A 500-character X post and a 500-character email response have different structures, conventions, and jobs. Additional notes are optional.

Copilot CLI can confirm the agent sees it. Run these inside a Copilot CLI session:

```text
/skills list
/skills info konvo
```

If you edit the skill mid-session, `/skills reload` picks up the change without a restart.

### 3. 📝 Or hand it a draft you already wrote

Paste the draft and say what you want. You do not need to spell out the ground rules:

> Use the KONVO skill to improve this draft.

Keeping your voice, not inventing expertise, not quietly replacing your argument, and flagging the weak spots before rewriting are all default behavior now. You get back a short list of flags first, then the revision:

- claims that need checking, with the line quoted
- confusing or abrupt sections
- generic AI-sounding phrases
- missing context
- places where a diagram or example would help

Then the changes that mattered, then the revised draft.

If you want it to skip the review and just hand back prose, say so. Your prompt overrides the defaults:

> Just give me the revised version, no commentary.

### 4. ✂️ Or paste something short and ask for a cleanup

The same skill handles short-form, and it skips the interview when you do this, because your draft already tells it the topic and the goal:

> clean this up: been debugging for hours and it turns out the api wasn't slow because of the database, we were opening a new connection per request

You get back something the size of what you gave it. Not an article about connection pooling.

This covers posts and threads for X, LinkedIn posts, forum and Stack Overflow replies, Slack and Discord messages, text messages, and email. For social specifically, it handles the fiddly parts: hooks that say something instead of announcing a topic, per-post character counts you can actually trust, which post each image attaches to, and keeping links out of the main post so the algorithm doesn't bury it.

The short-form rules are not guesses about what sounds human. They were measured against 809 real forum replies written between 2006 and 2026, about 27,000 words. That corpus is where the specific numbers come from: the median reply is 139 characters, 58 percent are a single paragraph, and across all 809 there are zero headings. It is also why the machine-vocabulary ban list is in the skill at all, since 27 of the 29 banned words appear exactly zero times in 27,000 words of someone writing quickly and not thinking about it.

### 5. 🚧 Know when not to use it

`konvo` is tuned for explaining things: tutorials, guides, posts that build intuition before getting formal, and the short-form versions of all of that. Point it at a changelog or an API reference and you will get a friendly, chatty changelog, which is nobody's goal.

## 🧪 Running Evals

The default eval command is:

```bash
ruby evals/run_evals.rb run konvo
```

That creates both of these files by default:

- `evals/reports/konvo-YYYY-MM-DD.json`
- `evals/reports/konvo-YYYY-MM-DD.html`

The JSON file is the source of truth. The HTML file is the rendered report you can open directly in a browser.

## 🧭 Direction

The measure of KONVO is not whether the output sounds human. It is whether you would put your name on it.

That usually means the draft comes back with:

- less filler
- fewer canned transitions
- more specificity
- better rhythm
- clearer technical explanation
- your voice intact, and your judgment visible in what got emphasized

Then you edit it, because you are still the author. The skill is meant to hand you a strong draft and get out of the way, not to hand you something finished that you feel vaguely uneasy about publishing.
