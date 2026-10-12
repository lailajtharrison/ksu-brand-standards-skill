# ksu-brand-standards-skill

A Claude Code skill that carries the Kennesaw State University brand standards. Install it and Claude applies the official colors, fonts, logo rules, voice, and editorial style whenever you work on KSU-branded content.

**Status:** Active, as of 2026-10-12. The skill is in use and tracks the current edition of the brand guide.
**Owner:** Laila Harrison, KSU Office of Research.

## What it does

- **Brand platform.** Position statement, strategic vision, the four messaging pillars, and the brand story.
- **Verbal identity.** Personality keywords, six tone words with their boundaries, a tone meter by audience, headline examples, and long-form copy notes for athletics, research, and students.
- **Logo rules.** Master brand, the KS monogram and wordmark, five color variations, minimum size, clear space, transparency limits, and the full list of prohibited treatments.
- **Color palette.** Primary Gold `#ffc629` and Black `#2d2926`, five secondary colors, and two neutrals, each with Pantone, CMYK, and RGB values.
- **Typography.** Mars Extended, Bradford, Six Hands Brush, Montserrat, and Source Serif Pro, with roles, activated treatments, and the elevated-to-energized scale.
- **Brand elements, photography, web, and editorial.** Handmade Grit, Determined Textures, Exacting Excellence, iconography, photography direction by pillar, Omni CMS web rules, and Associated Press style notes.

## Quick start

Requires Claude Code. The skill is a single `SKILL.md` with no dependencies.

```bash
# Option 1: install for every project
cd ~/.claude/skills
git clone https://github.com/lailajtharrison/ksu-brand-standards-skill.git ksu-brand-standards

# Option 2: install for one project
cd your-project
mkdir -p .claude/skills
git clone https://github.com/lailajtharrison/ksu-brand-standards-skill.git .claude/skills/ksu-brand-standards
```

Option 3, from inside Claude Code:

```
/install-skill https://github.com/lailajtharrison/ksu-brand-standards-skill
```

Once installed, invoke it directly with `/ksu-brand-standards`. Or just ask Claude Code for help with KSU-branded content and the skill loads on its own.

## Repository layout

| Path | What lives here |
|------|-----------------|
| `SKILL.md` | The skill. Frontmatter plus six sections of brand standards and a contact table. |
| `README.md` | This file. |
| `docs/SPEC.md` | Requirements and how changes ship. |
| `.gitignore` | Ignores `.DS_Store` only. |

## How it works

- **Claude Code reads the frontmatter at session start.** The `name` and `description` fields in `SKILL.md` are what Claude sees before the skill loads.
- **The description decides when it triggers.** It names KSU and lists the content types that should pull the skill in: marketing, presentations, web pages, social media, and communications.
- **The whole body loads on trigger.** `SKILL.md` has no bundled reference files or scripts, so the full standards text enters context at once.
- **It is also a slash command.** `user-invocable: true` lets you call `/ksu-brand-standards` by hand.
- **Facts come from one source.** Everything in the body is drawn from the KSU Brand Standards Guide v10.4, 2025, published by the Office of Strategic Communications and Marketing.

## Configuration

There are no environment variables and no config files. The only settings are the frontmatter fields in `SKILL.md`.

| Field | Required | What it does |
|-------|----------|--------------|
| `name` | Yes | Skill identifier and slash command. Must be `ksu-brand-standards`. |
| `description` | Yes | Triggering text. Tells Claude when to load the skill. |
| `user-invocable` | No | Set to `true` so the skill can be called as a slash command. |

## Deploy / distribute

The skill is distributed by git clone. Two copies exist: the personal repo under `lailajtharrison` and the org copy under `ksu-oor`. Keep them in sync when the standards change.

## Related

- Personal repo: https://github.com/lailajtharrison/ksu-brand-standards-skill
- Org copy: https://github.com/ksu-oor/ksu-brand-standards-skill
- Claude Code docs: https://docs.anthropic.com/en/docs/claude-code
- KSU digital asset library: https://owlbrand.kennesaw.edu/
- Logo requests: logos@kennesaw.edu
- Brand questions: stratcomm@kennesaw.edu

## Spec

See [docs/SPEC.md](docs/SPEC.md) for requirements and how changes ship.
