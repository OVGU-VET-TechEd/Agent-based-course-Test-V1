# Task: create-session-skeleton

## Purpose
Generates a new **Session Skeleton** file in the `skeletons/` folder.
This is a placeholder to be filled in later.

## Inputs
- Session number (e.g., "01")
- Session type (e.g., "lecture" or "exercise")
- Session title (e.g., "Introduction to Data")

## Output
- `skeletons/{number}-{type}.md` (e.g., `skeletons/01-lecture.md`)
- Structure based on `templates/session-skeleton.yaml`

## Steps
1. Get session number, type, and title from the user's command.
2. Load `templates/session-skeleton.yaml`.
3. Fill in the template placeholders with the provided inputs.
4. Save the new file to the `skeletons/` directory.
5. Confirm to the user that the skeleton file has been created.