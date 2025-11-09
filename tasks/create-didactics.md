# Task: create-didactics

## Purpose
Creates the **Lecture Didactics & Style** document.
Defines pedagogical concept, professor persona, style and course type.
Builds on Lecture Outline to ensure consistent teaching strategy.

## Inputs
- Summary from `docs/lecture-outline.md`
- Target audience from `docs/lecture-outline.md`
- Learning objectives from `docs/lecture-outline.md`

## Output
- `docs/lecture-didactics.md` (Markdown file)
- Structure based on `templates/lecture-didactics-template.yaml`

## Steps
1. Read abstract, audience, time commitment and learning objectives from outline
2. Design appropriate didactic concept (teaching methods, learning phases)
3. Describe professor persona (expertise, role, style)
4. Define style & difficulty level (humorous, academic, practice-oriented, etc.)
5. Determine course type (introduction, scientifically advanced, application-oriented, group work, self-study)
6. Fill template `templates/lecture-didactics-template.yaml` with results
7. Save file as `docs/lecture-didactics.md`