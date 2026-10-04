# AgentStage 🎭

Dynamically install and switch multi-agent environments, roles, tones, and custom personas in your AI coding assistants with a single command. Switch instantly between strict technical workflows or fun pop-culture configurations (like *Automan*, *Mr. Robot*, *Pulp Fiction*, *Rick and Morty*, *Two and a Half Men*, *Futurama*, *The Avengers* or *Iron Man*).

## 🚀 Installation

Install this skill directly into your compatible development agent (Claude Code, Cursor, etc.) by running:

```bash
npx skills add juliocebrito/agentstage
```

To try a local checkout before publishing:

```bash
npx skills add ./ --list   # check the skill is detected
npx skills add ./          # install it
```

## 📦 Included stages

| ID | Persona | Focus |
|---|---|---|
| `default` | Senior Fullstack Engineer | Direct and technical, no persona |
| `automan` | Automan & the Cursor sub-agent | Retro-80s, witty perfect-AI humour |
| `mr_robot` | Elliot Alderson | Security, auditing, minimal dependencies |
| `pulp_fiction` | Winston Wolfe | High-pressure debugging and hotfixes |
| `rick_and_morty` | Rick Sanchez | Radical simplification and fast prototypes |
| `two_and_a_half_men` | Charlie & Alan Harper | The easy way versus what could go wrong |
| `futurama` | Bender | Automate every repetitive task |
| `avengers` | The Avengers | A team review from several angles |
| `iron_man` | Tony Stark & J.A.R.V.I.S. | Ship a Mark I that works, then upgrade it in versions |

You can edit or delete any of them except `default`, and `/stage reset` brings back the original. Stages you create yourself are marked 🛠️ in the menu, included ones 📦, and modified included ones ✏️.

## 🛠️ Usage

| Command | What it does |
|---|---|
| `/stage` | Show the interactive menu |
| `/stage <stage_ID>` | Switch to a stage (also turns the persona back on) |
| `/stage new` | Create a custom stage through a 3-question interview |
| `/stage edit <stage_ID>` | Change a stage's role, tone or focus (any stage except `default`) |
| `/stage reset <stage_ID>` | Undo your changes to an included stage, or bring back one you deleted |
| `/stage delete <stage_ID>` | Delete a stage after confirmation (not `default`, not the active one) |
| `/stage fav <stage_ID>` / `/stage unfav <stage_ID>` | Pin a stage to the ⭐ Favorites group at the top of the menu, or unpin it |
| `/stage off` | Drop the persona: same as `/stage default` |

You can also ask in plain words ("edit the mr_robot stage", "add futurama to my favourites", "turn the persona off").

In Claude Code, `/stage` is rejected as an unknown command: use `/agentstage` instead, with the same arguments (`/agentstage`, `/agentstage mr_robot`, `/agentstage edit mr_robot`…).

Your choices (active stage, favourites, custom stages and changes to included ones) are saved in an `agentstage.json` file at your project's root the first time you change something. Included stages are never copied there, so updating the skill brings you new and improved ones without touching your setup. Add it to `.gitignore` if you don't want it in the repository.

A stage only changes the assistant's tone and focus: project rules, tests and confirmations still apply, and code is never written in character.
