# Task: create-outline

## Purpose
Creates the **Lecture Outline** as starting point for a lecture.
Defines title, audience, abstract, learning objectives and optional logo.

## Inputs
- Lecture title
- Target audience (e.g., students, professionals, beginners)
- Time commitment (e.g., semester hours, total hours)
- Abstract (topics, content, benefits)
- Learning objectives (3-5 concrete goals)
- Logo (optional, as prompt)

## Output
- `docs/lecture-outline.md` (Markdown file)
- Structure based on `lecture-outline-template.yaml`

## Steps
1. Capture title, audience, time commitment and abstract
2. Define 3-5 concrete learning objectives
3. Optional: Add logo prompt
4. Fill template `lecture-outline-template.yaml` with inputs
5. Save file as `docs/lecture-outline.md`