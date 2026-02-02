# BMAD & Claude Skills Collection

A curated collection of BMAD (Build My AI Developer) skills and workflows for Claude Code, designed to enhance AI-assisted software development and creative problem-solving.

## Overview

This repository contains reusable skills and workflows that can be invoked within Claude Code to automate and streamline various development tasks, from brainstorming and planning to implementation and testing.

## Project Structure

```
bmad-claude-skills/
├── _bmad/                          # BMAD skills and workflows
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
├── .claude/                        # Claude Code configuration
└── README.md                       # This file
```

## Configuration

The global configuration is managed in `_bmad/core/config.yaml`:

```yaml
user_name: Jitera
communication_language: English
document_output_language: English
output_folder: "{project-root}/_bmad-output"
```

**Version**: 6.0.0-Beta.1

## Available Skills

### Core Workflows

- **brainstorming** - Facilitate interactive brainstorming sessions using diverse creative techniques and ideation methods
- **party-mode** - Orchestrate group discussions between multiple agents for collaborative problem-solving
- **advanced-elicitation** - Advanced requirement elicitation and analysis

### BMM (BMAD Methodology Manager) Workflows

#### Planning Phase
- **create-prd** - Create comprehensive Product Requirements Documents
- **create-ux-design** - Design user experience patterns and workflows

#### Solutioning Phase
- **create-architecture** - Design system architecture and technical specifications

## Usage

### Using Skills in Claude Code

Skills can be invoked in Claude Code using the `/` command prefix:

```
/brainstorming
```

Or by asking Claude directly:
```
Can you help me brainstorm ideas for...
```

### Workflow Structure

Each workflow is defined with:
- **workflow.md** - Main workflow definition with YAML frontmatter
- **steps/** - Individual step files for workflow execution
- **templates/** - Output templates (if applicable)
- **resources/** - Supporting resources and data files

### Output Artifacts

All generated documents are saved to `_bmad-output/` organized by:
- `planning-artifacts/` - Documents from planning workflows
- `implementation-artifacts/` - Code and implementation outputs

## Adding New Skills

To add a new skill to this collection:

1. **Create a workflow directory**:
   ```
   _bmad/[module]/workflows/[your-skill-name]/
   ```

2. **Define the workflow** in `workflow.md`:
   ```markdown
   ---
   name: your-skill-name
   description: What this skill does
   context_file: '' # Optional
   ---

   # Your Skill Name

   **Goal:** Clear goal statement

   **Your Role:** Define the AI's role

   ...workflow instructions...
   ```

3. **Add step files** in `steps/`:
   ```
   steps/
   ├── step-01-initialization.md
   ├── step-02-execution.md
   └── step-03-completion.md
   ```

4. **Configure paths** in the workflow:
   ```markdown
   - `installed_path` = `{project-root}/_bmad/[module]/workflows/[your-skill-name]`
   - `default_output_file` = `{output_folder}/[category]/[output-name].md`
   ```

5. **Test the workflow** by invoking it in Claude Code

## Best Practices

- **Modular Design** - Keep workflows focused on a single purpose
- **Step-based Execution** - Break complex workflows into manageable steps
- **Clear Documentation** - Document role, goals, and expected outcomes
- **Template Driven** - Use templates for consistent output formatting
- **Configuration** - Leverage config.yaml for user preferences
- **Output Organization** - Save artifacts to appropriate output directories

## Contributing

When adding new skills:
1. Follow the existing workflow structure patterns
2. Include comprehensive documentation in the workflow file
3. Add clear step definitions with user control points
4. Test thoroughly before committing
5. Update this README with new skill descriptions

## License

[Specify your license here]

## Version History

- **6.0.0-Beta.1** (2026-01-26) - Initial BMAD installation
- Current - Added README and project documentation

## Contact

Maintained by: Jitera

---

**Note**: This is a living collection. Skills and workflows will be added continuously to expand capabilities for AI-assisted development.
