---
name: transcript-study-pack
description: "Converts transcript-based source material into structured study files: `outline.md`, `quiz.json`, `quiz.md`, `summary.md`, and final folder organization. Use when the user wants lecture-style notes from a transcript, multiple-choice quiz generation, Mochi-compatible quiz markdown, source summaries, or organized author/date/title study-pack folders."
---

# Transcript Study Pack

## How To Invoke

Invoke this skill whenever the user asks for any part of the transcript-to-study-pack workflow.

Common direct requests:

- "Use the `transcript-study-pack` skill."
- "Turn this transcript into an `outline.md`."
- "Make a quiz from this transcript."
- "Convert `quiz.json` into Mochi markdown."
- "Write a short `summary.md` from this outline."
- "Organize these study-pack files into the final folder."

Automatic triggers:

- The request mentions a transcript plus one of `outline.md`, `quiz.json`, `quiz.md`, or `summary.md`.
- The request asks for lecture notes, study notes, quiz generation, Mochi cards, or transcript-based summaries.
- The request asks to move transcript study files into author/date/title folders.

## Use This Skill When

- The source is a transcript from a video, lecture, podcast, or article.
- The user wants `outline.md`, `quiz.json`, `quiz.md`, or `summary.md`.
- The user wants generated study files moved into an author/date/title folder.

## Working Rules

- Stay faithful to the source material. Do not invent facts, quotes, people, or dates.
- Prefer the repository's real output conventions over older prompt fragments when they conflict.
- If an earlier artifact already exists, read it and continue from there instead of regenerating upstream work.

## Workflow

1. Determine the starting artifact.
   - Raw transcript or `transcript.txt` -> create `outline.md`
   - `outline.md` exists -> create `quiz.json` and `summary.md`
   - `quiz.json` exists -> create `quiz.md`
   - Full study pack exists -> organize files
2. Read [formats.md](formats.md) before generating any file.
3. Read [organization.md](organization.md) before moving files.
4. Verify each output:
   - `outline.md` starts with `# <title>`, then `## Metadata`, then `## Detailed Outline`
   - `## Expected Outcome` uses the A+ student lead-in and concrete source-specific bullets under `Knowing`, `Reciting`, `Sharing`, and `Conversing`
   - `quiz.json` is valid JSON with 20-30 questions
   - `quiz.md` preserves quiz order and uses exact Mochi formatting
   - `summary.md` has frontmatter plus the four required sections

## Default Sequence

1. Produce `outline.md` from the transcript.
2. Produce `quiz.json` from `outline.md`.
3. Produce `quiz.md` from `quiz.json`.
4. Produce `summary.md` from `outline.md`.
5. Organize the files into the final destination folder if requested.
