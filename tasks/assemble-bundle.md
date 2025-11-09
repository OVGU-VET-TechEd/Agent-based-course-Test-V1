# Task: assemble-bundle

## Purpose
Packages the complete lecture (docs and materials) for distribution.

## Inputs
- All files in `docs/`
- All files in `materials/`

## Output
- A packaged file (e.g., `lecture-bundle.zip`) or a summary file.

## Steps
1. Agent asks for the desired bundle format (e.g., Zip).
2. Agent confirms which files to include (all from `docs/` and `materials/`).
3. Agent will then provide the user with the exact steps to create this bundle manually
   (e.g., how to create a Zip file of the folders), as the agent cannot
   directly create files on the user's file system.
4. Inform the user the workflow is complete.