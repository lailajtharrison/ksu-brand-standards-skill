# KSU Brand Standards — Claude Code Skill

A [Claude Code](https://docs.anthropic.com/en/docs/claude-code) skill that provides Kennesaw State University brand standards as contextual guidance when creating KSU-branded content.

When installed, Claude Code will automatically reference these brand guidelines when you're working on KSU-branded materials — marketing content, web pages, presentations, social media, or any communications using KSU identity.

## What's Included

- Brand platform, messaging pillars, and brand story
- Verbal identity — tone words, audience-specific tone adjustments, headline examples
- Logo usage rules — master brand, variations, sizing, spacing, prohibited treatments
- Color palette — primary (Gold `#ffc629`, Black `#2d2926`), secondary, and neutral colors with Pantone/CMYK/RGB values
- Typography — Mars Extended, Bradford, Six Hands Brush, Montserrat usage guidelines
- Brand elements — Handmade Grit, Determined Textures, Exacting Excellence, iconography
- Photography style direction by messaging pillar
- Web standards and editorial standards

## Installation

### Option 1: Add as a skill directory

```bash
# Clone into your Claude Code skills directory
cd ~/.claude/skills
git clone https://github.com/YOUR_USERNAME/ksu-brand-standards-skill.git ksu-brand-standards
```

### Option 2: Add to a project

```bash
# Clone into your project's .claude/skills directory
cd your-project
mkdir -p .claude/skills
git clone https://github.com/YOUR_USERNAME/ksu-brand-standards-skill.git .claude/skills/ksu-brand-standards
```

### Option 3: Install via Claude Code slash command

In Claude Code, run:
```
/install-skill https://github.com/YOUR_USERNAME/ksu-brand-standards-skill
```

## Usage

Once installed, invoke the skill in Claude Code:

```
/ksu-brand-standards
```

Or simply ask Claude Code to help with KSU-branded content — it will automatically apply the brand guidelines.

## Source

Based on the official KSU Brand Standards Guide (v10.4, 2025) from the Office of Strategic Communications and Marketing.

- **Logo requests**: logos@kennesaw.edu
- **Brand questions**: stratcomm@kennesaw.edu
- **Digital assets**: https://owlbrand.kennesaw.edu/
