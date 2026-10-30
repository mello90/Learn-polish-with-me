# Development roadmap

## Current capabilities

- Browser-based Polish vocabulary quiz
- Multiple-choice questions and randomized rounds
- Ten-question sessions
- Mistake review and quiz history
- Local progress and optional n8n Data Table sync

## Potential improvements

1. Add secure accounts and authorization for progress records.
2. Add validation, error handling, and rate limiting to webhook endpoints.
3. Add vocabulary topics and difficulty levels.
4. Introduce spaced repetition for frequently missed words.
5. Add automated tests for scoring, local storage, and sync behavior.
6. Optionally experiment with AI-generated explanations or example sentences, clearly marked as a future feature.

## Suggested tests

- Complete a ten-question round and verify score and history.
- Answer incorrectly and verify mistake review.
- Refresh and verify local progress is retained.
- Save and reload a player's history through n8n.
- Test malformed data and network failures.
- Test desktop and mobile layouts.
