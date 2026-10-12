# ksu-brand-standards-skill: specification

**Status:** v1.0, 2026-10-12. First written spec, reverse-engineered from the code as it stands.
**Owner:** Laila Harrison (KSU Office of Research). **Reviewer:** unassigned.
**Source of requirements:** `SKILL.md` and the existing `README.md`. The brand facts inside `SKILL.md` cite the KSU Brand Standards Guide v10.4, 2025, from the Office of Strategic Communications and Marketing. That guide is not in the repo.

This document is the contract for the code. Every change starts here: update the spec, then the code, then the tests, in one pull request. Each requirement has an ID and says how it is verified. **Auto** means a test checks it on every pull request. **Manual** means a reviewer checks it by hand before approving. **None** means nothing checks it today.

## 1. Purpose

Staff in the Kennesaw State University Office of Research use Claude Code to draft decks, web copy, social posts, and other branded material. Without guidance Claude guesses at colors, fonts, and logo rules. This skill puts the official standards in context so the first draft is already on brand. Done means that when the skill is active, Claude answers brand questions with the exact values from the guide and refuses to invent ones it does not have.

## 2. Scope

**In scope:** one `SKILL.md` that triggers on KSU-branded work, carries the brand platform, verbal identity, logo rules, color palette, typography, brand elements, photography direction, web standards, editorial standards, and the approval and contact paths.

**Out of scope:** logo files, font files, templates, or any binary assets. Automated enforcement or linting of produced content. Brand standards for any unit other than the university master brand. Sub-brand signatures for colleges or programs, beyond noting that they exist and who issues them. Keeping the skill in sync with future editions of the guide on its own.

## 3. Requirements

### Frontmatter (F)

| ID | Requirement | Verify |
|----|-------------|--------|
| F1 | `SKILL.md` begins with YAML frontmatter containing `name`, `description`, and `user-invocable`. | Manual: read the first five lines. |
| F2 | `name` is exactly `ksu-brand-standards` and matches the install directory name in the README. | Manual: compare `SKILL.md` and `README.md`. |
| F3 | `user-invocable` is `true`, so `/ksu-brand-standards` works as a slash command. | Manual: run the command in Claude Code. |
| F4 | No other frontmatter fields are present. | Manual: read the frontmatter. |

### Triggering (T)

| ID | Requirement | Verify |
|----|-------------|--------|
| T1 | The `description` names Kennesaw State University and the phrase "brand standards". | Manual: read the description. |
| T2 | The `description` lists the content types that should trigger it: KSU-branded content, marketing materials, presentations, web pages, social media, and communications. | Manual: read the description. |
| T3 | The `description` lists what the skill covers: logo usage, color palette, typography, brand voice, photography, graphic elements, and editorial standards. | Manual: read the description. |
| T4 | A request to make KSU-branded content loads the skill without the user naming it. | Manual: ask Claude Code for a KSU flyer in a fresh session and confirm the skill loads. |
| T5 | A request about an unrelated brand does not load the skill. | None. |

### Brand facts the skill must carry (B)

| ID | Requirement | Verify |
|----|-------------|--------|
| B1 | Primary colors are KSU Gold `#ffc629` and KSU Black `#2d2926`, each with Pantone, CMYK, and RGB values. | Manual: read the primary color table. |
| B2 | Secondary colors are Southern Polytechnic Green `#00843d`, Purple `#a682eb`, Orange `#f5873d`, Blue `#66abff`, and Neon Yellow `#ffff00`, with usage guidance to use them with restraint. | Manual: read the secondary color table. |
| B3 | Neutrals are Gray `#b2b4b2` and White `#ffffff`. The KS monogram outer stroke is PMS 421 Gray. | Manual: read the neutral table. |
| B4 | Brand typefaces are Mars Extended and Mars Semicondensed, Bradford Regular and Bold Italic, and Six Hands Brush, each with a stated role. | Manual: read the typography tables. |
| B5 | Legacy typefaces still in use are Montserrat and Source Serif Pro. Montserrat is required for all web content. | Manual: read the typography and web sections. |
| B6 | The logo is the KS monogram plus the Kennesaw State University wordmark, in vertical and horizontal forms, always with the registered mark. | Manual: read section 3. |
| B7 | The five logo variations and their backgrounds are listed. White Color is required on dark backgrounds. Black Color is for light backgrounds. | Manual: read the variation table. |
| B8 | Minimum logo size is 1 inch. Clear space is one sixth of the KS monogram height. | Manual: read the sizing and spacing rules. |
| B9 | Transparency is allowed only on single-color black or white monograms, at 10 to 20 percent, over graphic backgrounds, never over photos. | Manual: read the transparency rules. |
| B10 | The prohibited treatments list includes disassembling, rotating, grayscale, drop shadow or stroke, busy backgrounds, stretching, changed typefaces, white box, white outer stroke, redrawing, and cropping. | Manual: read the unacceptable treatments list. |
| B11 | The seal is restricted to formal and ceremonial use. Owl and athletic marks are for athletics only. Custom owl graphics are not allowed. | Manual: read the seal and athletics sections. |
| B12 | The six tone words are Bold, Humble, Proud, Resilient, Bright, and Accomplished, each paired with the boundary it must not cross. | Manual: read the tone word table. |
| B13 | The four messaging pillars are Made to Meet the Moment, Powering Our Communities, Guided by Excellence, and Together, for Better. | Manual: read the pillar table. |
| B14 | The tone meter gives lead tone words for prospective students, faculty and staff, peers, and industry partners. | Manual: read the tone meter. |
| B15 | Editorial rules follow the Associated Press Stylebook. First reference is "Kennesaw State University", then "Kennesaw State" or "KSU", never "Kennesaw" alone. | Manual: read section 6. |
| B16 | Web rules require the Omni CMS template, Montserrat, seven to eight top-level nav items, two dropdown levels, and WCAG 2.0 AA. | Manual: read section 5. |
| B17 | The skill states that all materials using the KSU identity need review by the Office of Strategic Communications and Marketing, and gives the request link, logo address, questions address, and phone. | Manual: read the header and the contact table. |
| B18 | The skill cites its source edition, Brand Standards Guide v10.4, 2025. | Manual: read the header. |

### Correct answers when active (A)

| ID | Requirement | Verify |
|----|-------------|--------|
| A1 | Asked for a KSU color, Claude gives the exact hex, Pantone, CMYK, or RGB from the tables. It never approximates or invents a value. | Manual: ask for KSU gold and compare to B1. |
| A2 | Asked which logo to use on a dark background, Claude answers the White Color version. On gold, white, or gray it offers Black Color or Two Color. | Manual: ask both cases. |
| A3 | Claude never recommends a treatment on the prohibited list, such as grayscale, drop shadow, stretching, or a white box. | Manual: ask Claude to put the logo in a white box and confirm it declines and explains. |
| A4 | Asked for a font, Claude picks from the brand or legacy set and gives Montserrat for web body copy. | Manual: ask for a web heading and body font. |
| A5 | Drafted copy uses the tone words, the pillar framing, and the first-reference rule for the university name. | Manual: request a short paragraph and check. |
| A6 | Claude reminds the user that finished materials need StratComm approval and gives the request link. | Manual: request a flyer and look for the reminder. |
| A7 | When a fact is not in `SKILL.md`, Claude says so and points to stratcomm@kennesaw.edu instead of guessing. | Manual: ask about a sub-brand signature for a specific college. |
| A8 | Claude keeps gold and black predominant and uses secondary colors sparingly. | Manual: ask for a palette for a poster. |

### Install and runtime (I)

| ID | Requirement | Verify |
|----|-------------|--------|
| I1 | Cloning the repo into `~/.claude/skills/ksu-brand-standards` makes the skill available in every project. | Manual: clone and open any project. |
| I2 | Cloning into `<project>/.claude/skills/ksu-brand-standards` makes it available in that project only. | Manual: clone and open that project. |
| I3 | The skill needs no dependencies, scripts, network calls, or environment variables. | Manual: confirm the repo has only `SKILL.md`, `README.md`, `.gitignore`, and `docs/`. |
| I4 | The repo holds no credentials. Contact details are public office addresses only. | Manual: grep the repo. |

## 4. Interfaces

### Frontmatter

| Field | Value |
|-------|-------|
| `name` | `ksu-brand-standards` |
| `description` | Triggering text. See T1 to T3. |
| `user-invocable` | `true` |

### Install paths

| Scope | Path |
|-------|------|
| All projects | `~/.claude/skills/ksu-brand-standards/SKILL.md` |
| One project | `<project>/.claude/skills/ksu-brand-standards/SKILL.md` |
| Slash command | `/ksu-brand-standards` |
| Documented alternative | `/install-skill <repo url>` as written in the README |

### Sections of `SKILL.md`

| Section | Contents |
|---------|----------|
| Header | Approval statement, request link, contacts, asset library |
| 1. Brand Platform | Position statement, strategic vision, pillars, brand story |
| 2. Verbal Identity | Personality keywords, tone words, tone meter, headline examples, long-form copy |
| 3. Logos & Usage | Master brand, monogram, wordmark, variations, sizing, spacing, transparency, prohibited treatments, extensions, seal, athletics |
| 4. Visual Identity | Colors, typography, activated type, scales, brand elements, photography |
| 5. Web Standards | Omni CMS, navigation, typography, writing, accessibility |
| 6. Editorial Standards | AP style rules, university name usage |
| Quick Reference | Contact table |

Environment variables: none.

## 5. Open decisions

1. Two remotes exist, `lailajtharrison` and `ksu-oor`. Which one is canonical and how changes flow between them is not written down.
2. The README documents `/install-skill <url>` as a third install path. Whether that command exists in current Claude Code was not verified for this spec.
3. `SKILL.md` is about 17 KB in one file. Every trigger loads all of it. Splitting rarely used sections into reference files would cut context cost, but nothing requires it today.
4. The skill cites guide v10.4, 2025. There is no process for noticing when the Office of Strategic Communications and Marketing publishes a new edition.
5. No test checks triggering or answer accuracy. Everything in section 3 is manual.
6. The skill does not say where to obtain the licensed typefaces Mars, Bradford, and Six Hands Brush. Unknown whether that belongs here or with StratComm.
7. Reviewer is unassigned.

## 6. How changes ship

1. Open a branch. If behavior changes, update this spec first, in the same branch.
2. Open a pull request into `main`.
3. No CI today. Run the quick-start commands by hand before asking for review.
4. One approving review before merge.

## 7. Review log

None yet.
