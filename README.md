# BMAD & Claude Skills Collection

A curated collection of BMAD (Build My AI Developer) skills and workflows for Claude Code, designed to enhance AI-assisted software development and creative problem-solving.

## Overview

Reusable BMAD skills and workflows for Claude Code, covering brainstorming, planning, architecture, development, testing, and project management.

## Project Structure

```
bmad-claude-skills/
├── .claude/                        # Claude Code skills and configuration
│   ├── commands/                  # Command-style skills (reference workflows)
│   │   ├── bmad_brainstorming.md
│   │   ├── bmad_bmm_create-prd.md
│   │   └── ... (47 skills)
│   ├── skills/                    # Full skill packages
│   │   ├── js-clean-code/        # JavaScript best practices
│   │   ├── react-best-practices/ # React/Next.js guidelines
│   │   └── ui-ux-pro-max/        # UI/UX design system
│   └── settings.local.json       # Claude Code permissions & config
├── _bmad/                          # BMAD workflow implementations
│   ├── core/                       # Core BMAD workflows
│   │   ├── config.yaml            # Global configuration
│   │   ├── tasks/                 # Task definitions
│   │   ├── resources/             # Shared resources (Excalidraw, etc.)
│   │   ├── workflows/             # Core workflow definitions
│   │   │   ├── brainstorming/    # Creative brainstorming sessions
│   │   │   ├── party-mode/       # Multi-agent discussions
│   │   │   └── ...
│   │   └── agents/                # Agent definitions
│   └── bmm/                        # BMAD Methodology Manager workflows
│       └── workflows/             # BMM-specific workflows
│           ├── 2-plan-workflows/  # Planning phase workflows
│           │   ├── create-prd/   # Product requirements
│           │   └── create-ux-design/ # UX design workflows
│           └── 3-solutioning/     # Solution design workflows
│               └── create-architecture/ # Architecture design
├── _bmad-output/                   # Generated artifacts
│   ├── planning-artifacts/        # Planning documents
│   └── implementation-artifacts/  # Implementation outputs
└── README.md                       # This file
```

## Configuration

Global config: `_bmad/core/config.yaml`
Output folder: `_bmad-output/`
Permissions: `.claude/settings.local.json`

## Available Skills

### Full Skills (`.claude/skills/`)
- **js-clean-code** - JavaScript/TypeScript best practices
- **react-best-practices** - React/Next.js guidelines
- **ui-ux-pro-max** - UI/UX design system

### Command Skills (`.claude/commands/`)
45+ BMAD workflows including:
- **Planning** - Product briefs, PRDs, UX design
- **Architecture** - System design, diagrams, wireframes, flowcharts
- **Development** - Epics, stories, specs, code review
- **Testing** - Test design, automation, ATDD, NFR validation
- **Project Management** - Sprint planning, status, retrospectives
- **Utilities** - Brainstorming, research, editorial review

## Usage

Invoke skills with `/` slash commands:
```
/bmad_brainstorming
/bmad_bmm_create-prd
```

### Skill Types

**Command Skills** (`.claude/commands/*.md`) - Load workflows from `_bmad/`
**Full Skills** (`.claude/skills/*/`) - Self-contained skill packages

Output saved to `_bmad-output/`

## Adding New Skills

### Option 1: Command Skills (Reference BMAD Workflows)

1. **Create a command file** in `.claude/commands/bmad_your-skill.md`:
   ```markdown
   ---
   description: 'Brief description of what this skill does'
   ---

   LOAD the FULL @_bmad/core/workflows/your-skill/workflow.md and follow its directions exactly!
   ```

2. **Create the workflow** in `_bmad/core/workflows/your-skill/workflow.md` with steps, templates, etc.

### Option 2: Full Skills (Self-Contained)

Create a directory in `.claude/skills/your-skill/` with:
- `SKILL.md` - Main skill instructions
- `metadata.json` - Skill metadata
- `README.md` - Documentation
- `rules/` - Optional rule files

### Update Permissions

Add your skill to `.claude/settings.local.json`:
```json
"permissions": {
  "allow": [
    "Skill(your-skill)"
  ]
}
```

## Version

**6.0.0-Beta.1** (2026-01-26)

---

**Note**: This is a living collection. More skills will be added over time.
