# Task: validate-lecture

## Purpose
Performs a quality check on all lecture files for consistency.

## Inputs
- `docs/lecture-outline.md`
- `docs/lecture-didactics.md`
- `docs/lecture-agenda.md`
- All files in `materials/`
- `checklists/lecture-quality-checklist.md`

## Output
- `docs/validation-report.md`

## Steps
1. Read the `checklists/lecture-quality-checklist.md`.
2. Check if all Learning Objectives from the outline are covered in the agenda and materials.
3. Check if the professor persona and style are used consistently in the materials.
4. Check for broken file links or mismatches between the agenda and the `materials/` files.
5. Check `materials/` files for basic LiaScript syntax errors based on `data/liascript-cheat-sheet.md`.
6. Write all findings into a new file: `docs/validation-report.md`.
7. Inform the user that the validation report is complete.