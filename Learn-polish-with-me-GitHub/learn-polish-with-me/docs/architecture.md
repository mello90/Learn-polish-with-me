# Architecture

The application serves an interactive quiz directly from an n8n webhook. The browser runs the quiz logic and keeps local progress; two additional webhook routes support remote progress synchronization.

## Request flow

1. **GET `/webhook/learn-polish`**: n8n responds with the quiz HTML/CSS/JavaScript.
2. **Browser**: JavaScript presents multiple-choice questions, evaluates answers, maintains a mistake list and records completed rounds.
3. **Browser `localStorage`**: Stores progress for use on the same browser.
4. **GET `/webhook/learn-polish-load`**: Requests stored progress from n8n, which reads an n8n Data Table and returns a response.
5. **POST `/webhook/learn-polish-save`**: Sends progress to n8n, which upserts a row in the Data Table.

## Components

| Component | Responsibility |
| --- | --- |
| Quiz interface | Questions, answers, feedback, mistake practice, history |
| Webhook (quiz) | Serves the browser application |
| Webhook (load) | Loads saved progress |
| Webhook (save) | Persists progress |
| n8n Data Table | Stores progress keyed by a player display name |

## Data model

The original workflow uses a player display name and serialized progress/history values. Confirm actual field names and types from the sanitized export before importing into a new instance.

## Boundaries

The display name is **not an authentication mechanism**. Public webhook access should be restricted or hardened before handling real user data. The quiz content is predefined rather than AI-generated.
