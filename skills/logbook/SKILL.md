---
name: logbook
description: "Use when saving the history of a Socratic exploration or brainstorming session. Also invocable standalone to document decisions from any exploration."
---

# Logbook

Save the history of a Socratic exploration or brainstorming session.

## Purpose

Create a document that preserve the interactions between the user and you. The document will include your questions, the user's answers and inputs, your responses. You won't alter the history. This serves as a record of the exploration process and to track the evolution of ideas. This is not a summary or a rationale document - it's a log of what actually happened during the session, warts and all, in chronological order.

## Input

The whole session history, including:

- Questions asked by the agent.
- User's answers and inputs.
- Agent's responses.
- Any other interactions that occurred during the session.
- Eventually, errors or misunderstandings that happened along the way.

## Output

Save the document to: `docs/superpowers/logbooks/YYYY-MM-DD-<topic>-logbook-<sequence_number>.md`.
Do not overwrite existing files. Append a sequence number if needed (first file does not need a `sequence_number`).

(User preferences for document location override this default)

## Document Structure

Organize the received data into these sections:

### Required sections (always include):

- **Topic** — the session topic.
- **Logbook** — the session history, as defined. This is the core of the document and should be preserved as faithfully as possible.

### Optional sections (include if relevant):

- **Trigger** — what triggered logbook generation (e.g. the context was about to be cleared, the user requested to save the session, etc.)

## Writing Style

- Write exactly what happened during the session, without alteration or editorializing. This is a log, not a narrative or rationale document.
- Do not editorialize or add the agent's opinion.
- Keep it chronological and faithful to the actual interactions that occurred.
- Be complete.

## Process

1. Gather the whole session history.
2. Organize into the document structure above.
3. Write the document.
4. Save to the logbooks directory.
5. Commit to git.

## Trigger

- Invoked by brainstorming after the user reviewed written spec (before transitioning to implementation).
- Also invocable standalone to generate a logbook document from any Socratic exploration.
- Can be triggered by the user at any time to document a session, even if not part of the brainstorming process.
- Should be triggered before the context reaches maximum capacity, or before compacting or clearing the context (`/compact`, `/clear`), to preserve the full context of the exploration.
