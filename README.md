# AI D&D Obsidian Toolkit

> **AI-powered instructions and skills for managing D&D 5E campaigns using Claude, Gemini, and other AI agents, seamlessly integrated with Obsidian.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![AI Agents](https://img.shields.io/badge/AI-Claude%20%7C%20Gemini%20%7C%20ChatGPT-blue)](https://github.com/Tezumeto/ai-dnd-obsidian-toolkit)
[![D&D 5E](https://img.shields.io/badge/D%26D-5E%20%7C%205.5-red)](https://dnd.wizards.com/)

---

## 📖 About

This repository contains a comprehensive system of AI instructions, skills, and workflows designed to help Dungeon Masters manage D&D campaigns with the assistance of AI agents (Claude, Gemini, ChatGPT, Deepseek).

**Key Features:**
- 🤖 Multi-agent support with consistent instructions
- 📝 6+ specialized skills for common DM tasks
- 🗂️ Obsidian vault integration
- 📊 Git versioning for instruction evolution
- 🎨 Image prompt generation for character/location art
- 🎲 Session processing from recordings to player-ready recaps

**Built for:** Val'trey D&D setting (but easily adaptable to any campaign)

---

## 🗂️ Structure

```
.llm/
├── prompts/
│   ├── system.md              # Core system prompt (all agents)
│   └── agent_template.md      # Template for new agents
├── skills/
│   ├── npc_creation.md        # Create NPCs with full details
│   ├── image_prompt.md        # Generate prompts for AI art
│   ├── lore_expansion.md      # Expand world lore with consistency checks
│   ├── location_design.md     # Design cities, dungeons, landmarks
│   ├── item_creation.md       # Create balanced magic items
│   └── session_processing.md  # Process session recordings into recaps
├── .gitignore                 # Exclude operational data
└── README.md                  # This file
```

**Excluded from Git:**
- `summary/` — Session summaries (operational data)
- `log/` — Change logs (auto-generated)

---

## 🚀 Quick Start

### For AI Agents

1. **Read the system prompt:**
   ```
   .llm/prompts/system.md
   ```
   This contains the full context: setting, navigation rules, metadata structure, and skill usage.

2. **Use skills for specific tasks:**
   - Creating an NPC? → `skills/npc_creation.md`
   - Need an image prompt? → `skills/image_prompt.md`
   - Expanding lore? → `skills/lore_expansion.md`

3. **Follow documentation guidelines:**
   - Add changelog entries to modified files
   - Create session summaries for significant work
   - Commit changes with meaningful messages

### For Dungeon Masters

1. **Clone this repository:**
   ```bash
   git clone git@github.com:Tezumeto/ai-dnd-obsidian-toolkit.git
   cd ai-dnd-obsidian-toolkit
   ```

2. **Integrate with your Obsidian vault:**
   - Place `.llm/` in your vault root or campaign folder
   - Update paths in `prompts/system.md` if needed

3. **Configure AI agents:**
   - Point Claude Code to `CLAUDE.md` (create from template)
   - Point Gemini to `GEMINI.md` (create from template)
   - Use `agent_template.md` for other agents

4. **Start using skills:**
   - Ask your AI to read the relevant skill before tasks
   - Example: *"Read .llm/skills/npc_creation.md and create a tavern keeper for my port city"*

---

## 🎯 Skills Overview

### 1. NPC Creation (`npc_creation.md`)
Create detailed NPCs with:
- Frontmatter metadata (for Obsidian Dataview/Bases)
- Personality, history, connections
- Stat blocks (optional)
- Image prompts

**Use case:** *"Create a grizzled dwarf blacksmith for the capital city"*

---

### 2. Image Prompt Generation (`image_prompt.md`)
Generate prompts for AI art tools (Gemini, DALL-E, Midjourney):
- NPCs (portraits, 9:16)
- Locations (wide shots, 16:9)
- Items (detailed views, 1:1)
- Consistent style for series

**Use case:** *"Generate prompts for 5 city guards with different races"*

---

### 3. Lore Expansion (`lore_expansion.md`)
Expand worldbuilding with critical analysis:
- Check for contradictions with existing lore
- Ask hard questions about logic
- Suggest alternatives
- Link to existing elements

**Use case:** *"Develop the trade routes between these two kingdoms"*

---

### 4. Location Design (`location_design.md`)
Design cities, dungeons, and landmarks:
- Geography and climate
- Districts/rooms with details
- Key NPCs and factions
- Quest hooks

**Use case:** *"Create a coastal port city with a dark secret"*

---

### 5. Item Creation (`item_creation.md`)
Create balanced magic items:
- D&D 5E rarity guidelines
- Attunement requirements
- Stat blocks
- Lore and history

**Use case:** *"Design a legendary sword for a fallen hero"*

---

### 6. Session Processing (`session_processing.md`)
Convert session recordings into recaps:
- Full version (for DM, all details)
- Short version (for players, narrative style)
- Remove meta-information
- Transform mechanics into narrative

**Use case:** *"Process this NotebookLLM transcript into player-friendly recap"*

---

## 🤖 Supported AI Agents

| Agent | Primary Use | Status |
|-------|-------------|--------|
| **Claude (Sonnet 4.5)** | Text editing, narrative, lore, critical analysis | ✅ Active |
| **Gemini** | Image generation, video/audio analysis | ✅ Active |
| **ChatGPT** | Planned | 🔜 Future |
| **Deepseek** | Planned | 🔜 Future |

Add new agents using `prompts/agent_template.md`.

---

## 📊 Metadata & Obsidian Integration

All content uses structured frontmatter for Obsidian plugins:

```yaml
---
type: npc / location / item / event
name: Entity name
location: "[[City]]"
tags: [category1, category2]
created: 2024-01-01
author: claude
status: draft / reviewed / final
---
```

**Compatible with:**
- Obsidian Bases
- Dataview
- Graph view (wikilinks)

---

## 🔄 Git Workflow

Instructions are version-controlled for tracking evolution:

**Commit types:**
- `feat:` — New skill or functionality
- `update:` — Update existing file
- `fix:` — Fix error in instructions
- `refactor:` — Restructure without changing functionality
- `docs:` — Documentation changes

**Example:**
```bash
git commit -m "feat: add encounter_design skill

- Structure for combat/social/exploration encounters
- CR balance guidelines

Co-Authored-By: Claude Sonnet 4.5 <noreply@anthropic.com>"
```

---

## 🌍 Setting: Val'trey

This toolkit was built for the **Val'trey** D&D setting:
- A planet formed from the body of an Astral Whale
- Year: 1825 AR (After Rebirth)
- Tone: Dark fantasy to heroic fantasy (and comedy)
- Focus: Multi-racial port cities, cosmic horror elements, political intrigue

**Adaptable to any setting** — just update `prompts/system.md` with your world details.

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Report issues:** Found a bug or inconsistency? [Open an issue](https://github.com/Tezumeto/ai-dnd-obsidian-toolkit/issues)
2. **Suggest skills:** Have an idea for a new skill? Share it!
3. **Improve existing skills:** Submit a PR with enhancements
4. **Share your adaptations:** Using this for another setting? Tell us about it!

**Guidelines:**
- Follow the existing skill structure
- Test with at least one AI agent (Claude/Gemini/ChatGPT)
- Update README if adding new skills

---

## 📝 License

[MIT License](LICENSE) — Free to use, modify, and distribute with attribution.

---

## 🙏 Acknowledgments

- **Anthropic Claude** — Primary AI agent for text and narrative
- **Google Gemini** — Image generation and multimedia analysis
- **Obsidian** — Knowledge management platform
- **D&D Community** — For inspiration and best practices

---

## 📬 Contact

- **GitHub:** [@Tezumeto](https://github.com/Tezumeto)
- **Issues:** [Report here](https://github.com/Tezumeto/ai-dnd-obsidian-toolkit/issues)

---

**Made with ❤️ for the D&D AI community**
