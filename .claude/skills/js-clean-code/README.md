# JavaScript Clean Code

A structured repository for creating and maintaining JavaScript Clean Code principles optimized for agents and LLMs.

## Structure

- `rules/` - Individual rule files (one per rule)
  - `_sections.md` - Section metadata (titles, impacts, descriptions)
  - `_template.md` - Template for creating new rules
  - `category-description.md` - Individual rule files
- `metadata.json` - Document metadata (version, organization, abstract)
- __`AGENTS.md`__ - Compiled output (generated)
- __`SKILL.md`__ - Skill definition and usage guide

## Rule Categories

Rules are organized by category with specific prefixes:

1. **Variables** (`var-`) - Naming and declaration best practices
2. **Functions** (`func-`) - Function design and organization
3. **Objects** (`obj-`) - Object and data structure patterns
4. **Classes** (`class-`) - ES6 class design
5. **SOLID** (`solid-`) - SOLID principles for JavaScript
6. **Testing** (`test-`) - Testing best practices
7. **Concurrency** (`async-`) - Async/await and promises
8. **Error Handling** (`error-`) - Error management
9. **Formatting** (`format-`) - Code formatting conventions
10. **Comments** (`comment-`) - When and how to comment

## Creating a New Rule

1. Copy `rules/_template.md` to `rules/category-description.md`
2. Choose the appropriate category prefix:
   - `var-` for Variables (Section 1)
   - `func-` for Functions (Section 2)
   - `obj-` for Objects and Data Structures (Section 3)
   - `class-` for Classes (Section 4)
   - `solid-` for SOLID Principles (Section 5)
   - `test-` for Testing (Section 6)
   - `async-` for Concurrency (Section 7)
   - `error-` for Error Handling (Section 8)
   - `format-` for Formatting (Section 9)
   - `comment-` for Comments (Section 10)
3. Fill in the frontmatter and content
4. Ensure you have clear examples with explanations

## Rule File Structure

Each rule file should follow this structure:

```markdown
---
title: Rule Title Here
impact: MEDIUM
impactDescription: Optional description
tags: tag1, tag2, tag3
---

## Rule Title Here

Brief explanation of the rule and why it matters.

**Incorrect (description of what's wrong):**

```javascript
// Bad code example
```

**Correct (description of what's right):**

```javascript
// Good code example
```

Optional explanatory text after examples.

Reference: [Link](https://example.com)
```

## File Naming Convention

- Files starting with `_` are special (excluded from build)
- Rule files: `category-description.md` (e.g., `var-meaningful-names.md`)
- Section is automatically inferred from filename prefix
- Rules are sorted alphabetically by title within each section

## Impact Levels

- `CRITICAL` - Highest priority, major code quality and maintainability gains
- `HIGH` - Significant improvements to code quality
- `MEDIUM-HIGH` - Moderate-high gains
- `MEDIUM` - Moderate improvements
- `LOW-MEDIUM` - Low-medium gains
- `LOW` - Incremental improvements

## Acknowledgments

Based on [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript) by Ryan McDermott, adapted from Robert C. Martin's "Clean Code" principles.
