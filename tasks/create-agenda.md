# Task: create-agenda

## Purpose
Creates the **Lecture Agenda** as structured course plan.
Defines sessions/modules with title, duration, type, objectives, summary and materials files.
**Agent additionally adopts professor persona and style from `docs/lecture-didactics.md`**,
so all content is formulated in this voice.

## Inputs
- Learning objectives from `docs/lecture-outline.md`
- Abstract from `docs/lecture-outline.md`
- Time commitment from `docs/lecture-outline.md`
- Didactic concept from `docs/lecture-didactics.md`
- **Professor persona from `docs/lecture-didactics.md` (mandatory handoff)**
- **Style & difficulty from `docs/lecture-didactics.md` (mandatory handoff)**
- Course type from `docs/lecture-didactics.md`

## Output
- `docs/lecture-agenda.md` (Markdown file)
- Structure based on `templates/lecture-agenda-template.yaml`

## Steps
1. Read learning objectives from outline
2. Adopt didactic concept and course type from didactics
3. **Agent adopts professor persona & style from didactics into its own persona**
   - From this step, agent writes in professor persona tone
   - All agenda descriptions reflect this style
4. Define sessions/modules
5. Build agenda in structured form
6. Fill template `templates/lecture-agenda-template.yaml` with results
7. Save file as `docs/lecture-agenda.md`