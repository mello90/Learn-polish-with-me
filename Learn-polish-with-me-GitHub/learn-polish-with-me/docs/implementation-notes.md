# Implementation notes

## Design choices

- A predefined Polish vocabulary dataset avoids dependencies on external services and makes answers predictable.
- Each quiz round selects ten questions, with randomized ordering.
- Incorrect answers can be revisited in a dedicated practice flow.
- Browser storage enables local continuity; n8n Data Tables enable optional server-side synchronization.
- n8n webhooks act as lightweight application endpoints without a separate web server.

## Skills demonstrated

- Designing an interactive web interface with HTML, CSS, and JavaScript
- Connecting browser-side behavior to webhook-based workflows
- Managing application state and persistence
- Implementing load/save flows using n8n Data Tables
- Considering deployment, user experience, and security limitations

## Known limitations

**Authentication:** Player-name-based records are not private accounts. Someone else using the same name may be able to retrieve or overwrite a record.

**Input and output safety:** Validate webhook payloads and stored values. Render untrusted text using safe DOM APIs such as `textContent`, not interpolated `innerHTML`.

**Export hygiene:** Remove instance-specific IDs, Data Table identifiers, credentials, tokens, personal records, and embedded private URLs before publishing an exported workflow.

**AI claims:** No LLM integration is implemented in the described quiz workflow.
