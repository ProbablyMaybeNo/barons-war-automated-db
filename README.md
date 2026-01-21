WDC GIT HUB README

# Generic Wargaming Rules Repository  
*A web-app-first, BattleScribe-style rules + list-building data model*

---

## Overview

This repository specification defines a **generic, reusable format** for storing and serving tabletop wargame rules, army lists, and campaign systems in a way that is:

- **Web-app first** (UI components, dashboards, databases)
- **Modular and composable** (quick-reference panels, tables, procedures)
- **Compatible with BattleScribe / New Recruit concepts**
- **Versioned and living-rules friendly**
- **AI-generatable and AI-maintainable**

It is designed to power:
- Campaign trackers
- Rules reference dashboards
- Warband / army builders
- Combat simulators
- Narrative campaign systems

This is **not** a PDF mirror. It is a structured rules database.

---

## Core Design Principles

### 1. Atomic Rules
Rules are broken into small, linkable units:
- Rules
- Procedures
- Tables
- Glossary terms

This allows UI components to auto-populate exactly what players need.

### 2. Modular Rules Groups
Rules are bundled into **Rules Groups** (e.g. *Shooting Procedure*, *Hit Modifiers*, *Cover Saves*).  
Players and GMs can assemble custom reference panels instead of being forced into monolithic rule pages.

### 3. Live References (Default)
Campaigns reference the **latest rules by default**.
- Rules updates propagate automatically
- Breaking changes generate warnings (not hard locks)
- Optional snapshots can be handled at the app layer

### 4. BattleScribe-Style List Building
Army legality is enforced using:
- Slots
- Selectors
- Constraints (min/max/unique/requires/excludes/unlock)

The system intentionally avoids complex logic trees in v1 for clarity and portability.

### 5. Single-File Repo per Game
Each game is represented by **one JSON file**:
- Easier versioning
- Easier validation
- Easier AI generation

---

## Repository Structure (Logical)



## Generated Modules

- [Barons War - Conquest](./barons-war-conquest/rules.json)
- [Barons+War+2nd+edition+digital](./barons-war-2nd-edition-digital/rules.json)
- [Barons_War_-Death_and_Taxes](./barons-war-death-and-taxes/rules.json)
- [Outremer-digital-bookv1_0](./outremer-digital-bookv1-0/rules.json)
- [Outremer-Forces-of-Islam-BW2-bridging-v1](./outremer-forces-of-islam-bw2-bridging-v1/rules.json)
- [Outremer-Military-Orders-BW2-bridging-v1](./outremer-military-orders-bw2-bridging-v1/rules.json)
- [Outremer-Settled-Crusading-Franks-BW2-bridging-v1](./outremer-settled-crusading-franks-bw2-bridging-v1/rules.json)
- [The Barons' War Welsh Supplement](./the-barons-war-welsh-supplement/rules.json)
- [The_Barons'_War_Andy_Hobday_Second_Edition_Rulebook_OEF,_2025_05](./the-barons-war-andy-hobday-second-edition-rulebook-oef-2025-05/rules.json)

## AI Integration Index

For conversational UI integrations, use the AI index in `./ai`:

- `ai/catalog.json` lists modules and their section index files.
- `ai/section-index/*.json` maps stable section titles to JSON pointers in each `rules.json`.
- `ai/section-templates.json` defines canonical section labels to keep multiple repositories aligned.
- `ai/schema/*.schema.json` provides validation schemas.
