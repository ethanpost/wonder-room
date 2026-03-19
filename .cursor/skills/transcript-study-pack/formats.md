# Output Formats

Use these conventions when generating study-pack files.

## `outline.md`

Use the repository's current format:

```text
# <title>

## Metadata

- Author: <author or channel>
- Source: <url>
- Date: <YYYY-MM-DD when known>
- Folder: <folder name>

## Detailed Outline
```

Rules:

- Start the file with `# <title>`. Do not add `Title:` metadata lines above it.
- Follow immediately with a `## Metadata` section using bullet points in this exact label style:
  - `- Author: ...`
  - `- Source: ...`
  - `- Date: ...`
  - `- Folder: ...`
- After metadata, begin the notes under `## Detailed Outline`.
- Use `###` subsection headings plus bullets as needed under the detailed outline.
- Organize by major themes or topic shifts.
- Expand transcript fragments into clear notes.
- Include definitions, examples, arguments, counterarguments, background, and cause/effect when present.

After the main outline, include these sections:

- `## Core Ideas`
- `## Key Terms`
- `## People`
- `## Dates / Periods`
- `## Geography`
- `## Expected Outcome`

For `## Expected Outcome`, include:

- This lead-in sentence exactly:
  - `After taking notes from this outline and watching or listening to the source material, an **A+ student** would be capable of:`
- `### Knowing`
- `### Reciting`
- `### Sharing`
- `### Conversing`

Content guidance for the four subsections:

- `### Knowing`
  - Use concrete "would know / understand" bullets about major claims, arguments, frameworks, examples, and important context from the source.
  - Prefer 8-12 substantial bullets when the source supports it.
- `### Reciting`
  - Use short bullets about what the student should be able to summarize from memory in 30-60 seconds.
  - Focus on the main thesis, bottlenecks, sequences, or memorable frameworks.
- `### Sharing`
  - Use bullets that describe what the student should be able to explain or teach to someone else.
  - Frame these as practical peer-to-peer explanations, not as vague learning outcomes.
- `### Conversing`
  - Use bullets that describe what the student should be ready to discuss, compare, critique, or debate.
  - Frame these as thoughtful conversation prompts grounded in the source material.

Style rules for `## Expected Outcome`:

- Make the section read like the Elon Musk example: concrete, specific, and source-grounded.
- Do not write generic educational boilerplate such as "understand the topic" or "engage in discussion."
- Each bullet should name actual concepts, claims, tensions, examples, or debates from the source.

## `quiz.json`

Create a single JSON object:

```json
{
  "meta": {
    "title": "Title",
    "author": "Author or channel",
    "url": "https://example.com",
    "date": "2026-03-10"
  },
  "questions": [
    {
      "question": "Question text?",
      "options": ["Option A", "Option B", "Option C", "Option D"],
      "answer": "Correct option text"
    }
  ]
}
```

Rules:

- Generate 20-30 questions.
- Each question has exactly 4 options.
- Exactly 1 option is correct.
- `answer` must exactly match one item in `options`.
- Randomize the correct option position across questions.
- Prefer core concepts, reasoning, major claims, people, dates, and important examples.
- Do not invent metadata. Omit unknown optional fields.
- Prefer omitting fake timestamps like invented `generated_at` values.

## `quiz.md`

Convert `quiz.json` into exact Mochi-compatible markdown:

```text
## Question text here?

---

A) First option

B) Second option

C) Third option

D) Fourth option

---

Correct option text here

///
```

Rules:

- Preserve question order from `quiz.json`.
- Do not rewrite question or option wording.
- Map the 4 options in order to `A)` through `D)`.
- Put a blank line between question blocks.

## `summary.md`

Use YAML frontmatter with lowercase keys:

```yaml
---
title: Source title
author: Author or channel
url: https://example.com
date: 2026-03-10
---
```

Then include exactly these sections:

- `# Summary`
- `# Core Question`
- `# Key Concepts`
- `# Why It Matters`

Guidance:

- Keep the summary readable in about 30-60 seconds.
- State the central question or paradox clearly.
- List 3-6 key concepts.
- Explain why the topic matters in real-world or intellectual terms.
