# Workflow export

**The importable n8n workflow JSON is not included yet.** The original export must be inspected and sanitized before publication. Do not substitute a fabricated workflow file for the actual export.

## Publishing checklist

1. Export the workflow from n8n.
2. Remove or replace internal workflow/node/webhook identifiers and n8n instance-specific metadata as appropriate.
3. Remove credential references, secrets, production Data Table IDs, and any personal data.
4. Review embedded HTML/JavaScript for private URLs or identifiers.
5. Set the export to inactive and reconnect the Data Table after import.
6. Import into a test n8n instance and verify the three routes.
7. Commit the reviewed export as `workflow/learn-polish.json`.

## Expected endpoints

- `GET /webhook/learn-polish`
- `GET /webhook/learn-polish-load`
- `POST /webhook/learn-polish-save`

The Data Table must support storing progress and quiz history for a player. Check the original workflow for exact column names and payload shapes.
