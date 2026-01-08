# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is the documentation repository for **Papaours Gestion**, a French application for managing professional training programs and apprenticeship contracts. All content is written in **French**.

## Repository Structure

```
documentations/           # User documentation organized by feature/module
  accueil.md             # Main welcome page
  apprenant/             # Apprentice management
  employeur/             # Employer management
  contrats/              # Contract management
  dossier-formation/     # Training file management
  unite-formation/       # Training unit management
  gestion-droit/         # Access rights management
  gestion-documentaire/  # Document templates (substitutions, formatting, conditions)
  ...
release-notes/           # Version release notes (0.1.0, 0.2.0, etc.)
```

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

- **`index.md` files**: Define folder titles and icons only - they do NOT appear as links in navigation. Use `icon` property for Heroicons (e.g., `UserGroupIcon`, `DocumentTextIcon`)
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