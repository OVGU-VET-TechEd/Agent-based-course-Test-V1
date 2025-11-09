# Task: promote-session

## Purpose
Promotes a **Session Skeleton** to a full **Session Material** file.
It copies the skeleton content to the `materials/` folder as a starting point.

## Inputs
- Session number (e.g., "01")
- Session type (e.g., "lecture" or "exercise")

## Output
- `materials/{number}-{type}.md` (e.g., `materials/01-lecture.md`)

## Steps
1. Get session number and type from the user's command.
2. Find the corresponding file in `skeletons/` (e.g., `skeletons/01-lecture.md`).
3. Copy the content from that skeleton file.
4. Save this content to a new file in the `materials/` folder (e.g., `materials/01-lecture.md`).
5. Inform the user that the file is created and ready for co-authoring (`/coauthor-materials`).