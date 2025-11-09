# AI Agent Instructions - BMad-Method Lecture Project

## Project Overview
Educational content creation system implementing the **BMad-Method** - a structured workflow for lecture development: **outline → didactics → agenda → sessions → materials**. This is a task-driven authoring assistant, not a teaching platform.

## Architecture

### Template-Driven Content Generation
All content creation uses YAML templates in `templates/` combined with task specifications in `tasks/`:
- **Templates** define structure and output location (e.g., `lecture-outline-template.yaml` → `docs/lecture-outline.md`)
- **Tasks** define workflow steps and required inputs (e.g., `tasks/create-outline.md`)
- Templates use Jinja-style placeholders: `{{number}}`, `{{type}}`, `{{title}}`

### BMad-Method Workflow Stages
1. **Outline**: High-level lecture structure with learning objectives → `docs/lecture-outline.md`
2. **Didactics**: Teaching philosophy, pedagogical approach, professor persona → `docs/lecture-didactics.md`
3. **Agenda**: Time-bound session plan with types and objectives → `docs/lecture-agenda.md`
4. **Sessions**: Individual teaching units (skeleton → promoted to full content)
   - Skeletons: `skeletons/{number}-{type}.md` (minimal structure)
   - Materials: `materials/{number}-{type}.md` (full LiaScript content)
5. **Validation & Bundle**: Consistency check → final packaging

### Two-Stage Session Creation
1. **Skeleton** (`/create-session`) → Task: `create-session-skeleton.md` → Output: `skeletons/{number}-{type}.md`
2. **Promotion** (`/promote-session`) → Task: `promote-session.md` → Copies to `materials/{number}-{type}.md`

This prevents overwhelming users with large content blocks before confirming the session structure.

## Critical Workflows

### Command Execution Pattern
When user invokes a slash command (e.g., `/create-outline`):
1. Read corresponding task file from `tasks/` (e.g., `tasks/create-outline.md`)
2. Load referenced template from `templates/` if specified in the task
3. Gather required inputs interactively (never assume - always ask!)
4. Fill template with user-provided data
5. Write to output location specified in template's `output.filename`
6. Confirm completion before proceeding

**Example**: `/create-session 01 lecture "Introduction to AI"`
- Load `tasks/create-session-skeleton.md` + `templates/session-skeleton.yaml`
- Gather inputs: number=01, type=lecture, title="Introduction to AI"
- Output to `skeletons/01-lecture.md` with placeholder content

### Available Commands
- `/create-outline` - Initialize new lecture structure
- `/create-didactics` - Define pedagogical approach and teaching style
- `/create-agenda` - Build session timeline
- `/create-session {number} {type} {title?}` - Create session skeleton
- `/promote-session {number} {type}` - Expand skeleton to full material
- `/coauthor-materials` - Collaborative content refinement
- `/validate-lecture` - Consistency check across all components
- `/assemble-bundle` - Package complete lecture for delivery
- `/help` - List available actions
- `/exit` - Exit teaching agent mode

### Cross-Document Dependencies
Templates explicitly declare input dependencies:
```yaml
inputs:
  - docs/lecture-agenda.modules
  - docs/lecture-didactics.professor-persona
```
**When creating content**, read these dependency files first to ensure consistency.

### LiaScript Format Requirements
All `materials/*.md` files MUST use LiaScript syntax (reference: `data/liascript-cheat-sheet.md`):
- Slides separated by `---`
- Speaker notes use `{{1}}` notation
- Quizzes use `[(X)]` syntax for multiple choice
- Mermaid diagrams embedded in fenced code blocks
- **Critical**: New headings only inside HTML blocks, lists, or blockquotes (unless splitting slides)

### Professor Persona Adoption
When executing `/coauthor-materials`:
1. **Mandatory**: Load `docs/lecture-didactics.md` to extract professor persona and style
2. **Switch identity**: Write ALL content in that persona's voice
3. Maintain persona until task completion
4. Tone/style must match didactics definition (e.g., "humorous", "academic", "practice-oriented")

## Validation Requirements
`/validate-lecture` must check (see `checklists/lecture-quality-checklist.md`):
- **Traceability**: Each learning objective in outline appears in ≥1 session
- **Time consistency**: Sum of session durations ≈ outline's time-commitment
- **File alignment**: Every agenda session has corresponding `materials/{n}-{type}.md`
- **Persona consistency**: Materials reflect didactics style
- **LiaScript validity**: Check against `data/liascript-cheat-sheet.md` rules

Output findings to `docs/validation-report.md`.

## Agent Behavior Standards

### Interactive Dialog Model
- **Never dump large content blocks** - confirm structure first, then generate
- **Always present options as numbered lists** (e.g., "Choose: 1) Lecture 2) Workshop 3) Lab")
- **Ask for missing inputs** instead of making assumptions
- **Gate progression**: "I've completed [step]. Ready to proceed to [next step]?"

### Lazy Loading
**Do NOT** preload files on command invocation. Only read:
- Task definition file (mandatory)
- Referenced template (if creating content)
- Dependency files (when template specifies `inputs:`)
- User-specified files (when explicitly requested)

### Persona Mode
Default mode: Neutral assistant. When `/coauthor-materials` invoked: adopt professor persona from `docs/lecture-didactics.md` until user exits coauthoring.

## File Organization
```
docs/                          # Generated lecture documentation
  lecture-outline.md           # Created by /create-outline
  lecture-didactics.md         # Created by /create-didactics
  lecture-agenda.md            # Created by /create-agenda
  validation-report.md         # Created by /validate-lecture
skeletons/                     # Session placeholders
  {number}-{type}.md           # Created by /create-session
materials/                     # Full LiaScript content
  {number}-{type}.md           # Created by /promote-session
templates/                     # YAML structure definitions (5 templates)
tasks/                         # Workflow specifications (8 tasks)
data/liascript-cheat-sheet.md  # LiaScript syntax reference
checklists/                    # Quality validation rules
```

## Common Pitfalls
- ❌ Creating `materials/*.md` without first creating skeleton in `skeletons/`
- ❌ Generating content before gathering all required template inputs
- ❌ Writing markdown instead of LiaScript in materials files
- ❌ Ignoring professor persona when coauthoring
- ❌ Breaking LiaScript heading rules (no headings except in special contexts)
- ❌ Preloading all files instead of lazy loading per command
- ❌ Using wrong task file names (it's `create-session-skeleton.md` not `create-session.md`)
