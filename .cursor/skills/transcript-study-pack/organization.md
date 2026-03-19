# File Organization

Use this when the study-pack files need to be moved into their final folder.

## Required Files

Move these files together when they exist:

- `transcript.txt`
- `outline.md`
- `quiz.json`
- `quiz.md`
- `summary.md`

## Metadata Source

Read the metadata from `outline.md`:

- The `# <title>` heading at the top of the file
- The bullet values in the `## Metadata` section for:
  - `Author`
  - `Source`
  - `Date`
  - `Folder`

Use `Folder` as the parent directory.

## Destination Pattern

Create the child folder name as:

```text
YYYY-MM-DD_Title_With_Underscores_SourceID
```

Sanitizing rules:

- Keep the date as `YYYY-MM-DD`.
- Replace spaces and punctuation runs with underscores.
- Collapse repeated underscores to a single underscore.
- Trim leading or trailing underscores.
- Keep only letters, numbers, and underscores in the final name.

If the source URL contains a YouTube video ID, append it as the final segment.

Example:

```text
Stripe/2026-03-10_Bret_Taylor_of_Sierra_on_AI_agents_outcome_based_pricing_and_the_OpenAI_board_n4E4xNYCkYM
```

## Move Behavior

- Create the parent folder if needed.
- Create the destination folder if needed.
- Move the files without renaming them.
- Do not change file contents during organization.

## Inbox Workflow

If the files are being moved out of `_inbox`:

- Move the current `transcript.txt` with the rest of the study pack.
- Create a new blank `_inbox/transcript.txt` after the move so the inbox is ready for the next source.
