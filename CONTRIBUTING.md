# Contributing to AI D&D Obsidian Toolkit

Thank you for considering contributing! This toolkit is designed to help DMs and AI agents work together seamlessly.

---

## 🎯 Ways to Contribute

### 1. Report Issues
Found a bug, inconsistency, or improvement opportunity?
- [Open an issue](https://github.com/Tezumeto/ai-dnd-obsidian-toolkit/issues)
- Describe the problem clearly
- Include examples if possible

### 2. Suggest New Skills
Have an idea for a new specialized task?
- Open an issue with the `enhancement` label
- Describe the use case
- Explain what the skill should accomplish

### 3. Improve Existing Skills
Found a way to make a skill better?
- Fork the repository
- Make your changes
- Submit a Pull Request

### 4. Share Adaptations
Using this for another setting or system?
- Share your experience in Discussions
- Contribute setting-agnostic improvements

---

## 📐 Skill Structure Guidelines

When creating or modifying skills, follow this structure:

```markdown
# Skill: [Name]

## When to Use
[Clear description of when agents should use this skill]

## Context (what to read before starting)
[List of files/sections agents should read]

## Methodology
[Step-by-step instructions]

### 1. Questions to Ask
[Clarifying questions for the user]

### 2. File Structure
[Expected frontmatter and content structure]

### 3. Consistency Checks
[What to verify before finalizing]

## Examples
[2-3 concrete examples]

## Changelog
[Document skill version history]
```

---

## 🧪 Testing Your Contributions

Before submitting:

1. **Test with an AI agent**
   - Claude, Gemini, or ChatGPT
   - Verify the skill produces expected results

2. **Check consistency**
   - Does it follow existing patterns?
   - Is the language clear and unambiguous?

3. **Update documentation**
   - Add the skill to README.md
   - Update skill count and overview

---

## 📝 Commit Message Guidelines

Follow conventional commits:

```
<type>: <subject>

<body>

Co-Authored-By: [Your Name or AI] <email>
```

**Types:**
- `feat:` — New skill or functionality
- `update:` — Improve existing skill
- `fix:` — Fix error or bug
- `docs:` — Documentation only
- `refactor:` — Code restructure

**Examples:**
```
feat: add encounter_design skill

- Combat, social, and exploration encounters
- CR calculation guidelines
- Examples for levels 1-20

Co-Authored-By: Claude Sonnet 4.5 <noreply@anthropic.com>
```

```
update: improve NPC creation frontmatter

- Added alignment field
- Clarified organization field usage

Co-Authored-By: ChatGPT <noreply@openai.com>
```

---

## 🤖 AI-Generated Contributions

We welcome contributions from AI agents!

**Guidelines:**
- Clearly attribute AI involvement in commits
- User should review and approve before submitting
- AI should follow the same quality standards

**Example Co-Author line:**
```
Co-Authored-By: Claude Sonnet 4.5 <noreply@anthropic.com>
```

---

## 🔍 Pull Request Process

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/your-skill-name
   ```
3. **Make your changes**
4. **Test thoroughly**
5. **Commit with clear messages**
6. **Push to your fork**
7. **Open a Pull Request**
   - Describe what you changed and why
   - Reference related issues

---

## 📋 Code of Conduct

Be respectful and constructive:
- Welcome newcomers
- Provide helpful feedback
- Focus on improving the toolkit
- Respect different DM styles and preferences

---

## ❓ Questions?

- **GitHub Discussions:** Ask questions or share ideas
- **Issues:** For bugs or specific requests

---

Thank you for contributing! 🎲
