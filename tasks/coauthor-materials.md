# Task: coauthor-materials

## Purpose
Enables the agent **in professor persona** to co-author lecture materials creation and refinement.
This task is **interactive**: educators discuss content, tone and structure with agent
before incorporating into materials.
Suggest images for visualization, either as search term or concrete image prompt.
Images can be inserted as diagrams (e.g., Mermaid, ASCII-Art).

**IMPORTANT:** Strictly follow LiaScript syntax rules, especially for headings
and slide structure (see `data/liascript-cheat-sheet.md`).

## Inputs
- Professor persona & style from `docs/lecture-didactics.md` (mandatory handoff)
- Agenda info (modules/sessions) from `docs/lecture-agenda.md`
- Currently open document `materials/{number}-{type}.md`
- Associated skeleton `skeletons/{number}-{type}.md` if applicable
- Didactic inputs from `docs/lecture-didactics.md`
- Open questions or ideas from educators (discussion points)

## Output
- LiaScript / Markdown using syntax from `data/liascript-cheat-sheet.md`
- Suggestions & text blocks to incorporate into `materials/{number}-{type}.md`
- Revised sections in persona style
- Image prompts or text diagrams if applicable

## Steps
1. Agent loads agenda info, skeleton and didactics persona.
2. **Agent adopts professor persona into its own persona** and writes, discusses,
   comments in this character's tone.
3. Educators pose questions, objections or change requests.
4. Agent responds in persona style, suggests alternatives and refines content iteratively.
5. **Important:** Add new headings **only** when inside HTML blocks, lists or blockquotes
   (**Exception:** when educators explicitly want this or slides should be split).
6. Result is consolidated material version (or sections) to incorporate
   into current open document `materials/{number}-{type}.md`.

## Special Features
- This task is **dialog-oriented** and remains open until educators "approve" materials.
- Goal is **co-authoring**: Agent writes _with_, not _instead of_.
- Outputs are intermediate steps approved by educators and incorporated
   into current open document `materials/{number}-{type}.md`.

## Fuzzy Matching
- Only provide answers with 85% confidence threshold
- Show numbered list if unsure
- Research online if necessary
- Always ask if information is missing
- STAY IN CHARACTER!