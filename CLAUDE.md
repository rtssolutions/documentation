# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is the documentation repository for **Papaours Gestion**, a French application for managing professional training programs and apprenticeship contracts. All content is written in **French**.

The documentation is primarily **tutorial-style** (step-by-step guides for end users). It is also ingested by a **vector database (RAG)** to power an AI agent that helps users navigate and use the application. Keep this dual audience in mind: content must be clear for human readers and well-structured for semantic search/retrieval.

## Repository Structure

```
documentations/
  accueil.md               # Landing page
  prise-en-main/           # Getting started (navigation, first steps)
  apprenant/               # Apprentice management
    besoins-specifiques/   #   Specific needs sub-module
  employeur/               # Employer management
  contrats/                # Contract management
  dossier-formation/       # Training file management
  unite-formation/         # Training unit management
  formation/               # Training catalog
  financement/             # Financing / billing
  vente/                   # Sales
  comptabilite/            # Accounting
  gestion-droit/           # Access rights management
    acces-api/             #   API keys & machine access
    regles-assignation/    #   Assignment rules (roles, groups, users, machines)
  gestion-documentaire/    # Document templates
    template-document/     #   Template engine docs
      conditionner/        #     Conditional logic
      demarrer/            #     Getting started with templates
      formater/            #     Formatting helpers
      substituer/          #     Substitution variables
      tableau/             #     Table/array repetitions
  qualite/                 # Quality management
  historique/              # Activity history
  mes-taches/              # Task management
  mon-profil/              # User profile
  parametres/              # Settings
  aide-au-permis/          # Driving license assistance
  aide-contact/            # Help & contact
release-notes/             # Version release notes (0.1.0 → 0.8.0)
```

Modules can contain **nested subfolders**, each with their own `index.md`. This allows deep topic hierarchies (e.g., `gestion-droit/acces-api/01-introduction.md`).

## Markdown Format

All documentation files use Markdown with YAML frontmatter:

```markdown
---
title: "Required - displayed in menu and header"
description: "Optional - document description"
date: "Optional - YYYY-MM-DD format"
author: "Optional"
version: "Optional"
tags: ["optional", "array"]
icon: "Optional - Heroicons name, only for index.md files"
---

Content here...
```

### Key Conventions

- **`index.md` files**: Define folder titles and icons only - they do NOT appear as links in navigation. The `icon` property (Heroicons, e.g., `UserGroupIcon`, `DocumentTextIcon`) is optional and used only at the top-level module folders
- **Regular `.md` files**: Appear as clickable links in the sidebar
- **File naming**: Use `kebab-case` (e.g., `gestion-contrats.md`)
- **Numbered prefixes**: Used for ordering (e.g., `01-introduction.md`, `02-concepts.md`)
- **Internal links**: Use relative paths without `.md` extension (e.g., `[link text](17-formater-intervalles)`)

## Media and Diagrams

- **Images**: Standard markdown or HTML with dimensions: `![Alt](/images/file.png "WIDTHxHEIGHT")`
- **Videos**: HTML5 `<video>` tags with WebM/MP4 sources:
  ```html
  <video controls>
    <source src="/videos/tutorial.webm" type="video/webm" />
    <source src="/videos/tutorial.mp4" type="video/mp4" />
  </video>
  ```
- **Mermaid diagrams**: Supported with optional size hints (Tailwind classes or pixels):
  ```markdown
  ```mermaid "max-w-2xl"
  graph TD
      A[Start] --> B[End]
  ```
  ```
  Size options: `max-w-sm` to `max-w-7xl`, or `400px` to `1000px`

## Release Notes

Located in `/release-notes/` with semantic versioning (`0.1.0.md`, `0.2.0.md`, etc.). Follow the same YAML frontmatter format with `version` in metadata matching the filename.

## No Build Required

This repository contains only Markdown files consumed by the main Papaours Gestion application. There are no build commands, tests, or linting tools.