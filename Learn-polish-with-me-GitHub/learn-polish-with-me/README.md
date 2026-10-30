# Learn Polish with Me 🇵🇱

An interactive Polish vocabulary quiz built with **n8n, HTML, CSS, and vanilla JavaScript**.

**[Try the live quiz](https://mellows.app.n8n.cloud/webhook/learn-polish)**

## Features

- Polish vocabulary and phrase practice with multiple-choice answers
- Randomized ten-question quiz rounds
- Review of incorrectly answered questions
- Quiz history and progress tracking
- Browser-side persistence with `localStorage`
- Optional server-side progress synchronization using n8n webhooks and an n8n Data Table

## Technology

| Layer | Technology |
| --- | --- |
| User interface | HTML, CSS, vanilla JavaScript |
| Workflow/backend | n8n webhooks and response nodes |
| Persistence | Browser `localStorage` and n8n Data Tables |

## Architecture

```text
Browser quiz
   ├── GET  /webhook/learn-polish       → HTML quiz interface
   ├── GET  /webhook/learn-polish-load  → Load saved progress
   └── POST /webhook/learn-polish-save  → Save progress
                                             ↕
                                        n8n Data Table
```

See [architecture documentation](docs/architecture.md) for details.

## Project scope

This is a **workflow automation and web application project**. The current quiz uses a predefined vocabulary collection; it does **not** generate questions using an LLM. AI-generated exercises could be a future enhancement.

## Reproducing the project

The original n8n workflow export is **not included** in this ZIP because it has not yet been reviewed and sanitized for public release. To recreate the application, configure the three endpoints above, an HTML response node for the quiz, and Data Table lookup/upsert steps for progress persistence. See [workflow setup](workflow/README.md).

## Documentation

- [Architecture](docs/architecture.md)
- [Implementation notes and limitations](docs/implementation-notes.md)
- [Development roadmap](docs/development.md)
- [Workflow export checklist](workflow/README.md)
- [Screenshots guide](screenshots/README.md)

## Privacy and security

This is a learning prototype, **not a production account system**. Player-name-based progress syncing does not authenticate users. Do not store sensitive data. Production use would require authentication, input validation, authorization, safe rendering, and appropriate endpoint protection.
