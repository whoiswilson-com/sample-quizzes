# CLAUDE.md — Sample Quizzes Repository

This repository contains community-created sample study quizzes for [Who Is Wilson?](https://whoiswilson.app), a free quiz platform for exam preparation.

## What you're working with

Quiz files are **Markdown with YAML frontmatter**. Each file is a self-contained quiz that can be uploaded directly to whoiswilson.app or pasted into the in-browser editor.

## Quiz format

Every quiz file must follow this exact structure:

### Frontmatter

```yaml
---
title: "Quiz Title"
tags: [topic, subtopic]
time_limit: 30
allow_overrun: true
random_order: false
note: "Sample study questions — not affiliated with or sourced from official exams"
---
```

| Field | Required | Default | Description |
|-------|----------|---------|-------------|
| `title` | Yes | — | Quiz title displayed to the student |
| `tags` | No | `[]` | Lowercase tags for filtering, e.g. `[azure, identity, az-305]` |
| `time_limit` | No | untimed | Time limit in minutes. Omit or set to `0` for no time limit. |
| `allow_overrun` | No | `true` | If `true`, students can continue answering after the timer expires (answers still recorded). If `false`, the quiz auto-submits when time runs out. |
| `random_order` | No | `false` | If `true`, questions are shuffled into a random order for each attempt. |
| `note` | No | — | Displayed as a notice. For this repo, always include the disclaimer. |

`version` is accepted in frontmatter but ignored — the platform tracks versions automatically when a quiz is re-uploaded.

### Questions

Questions are separated by `---` (horizontal rule). Each question block:

```markdown
##### Question q001
type: single_choice
correct: [c]

Question stem text here. Full Markdown supported — **bold**, `code`, tables, etc.

A. First option
B. Second option
C. Third option
D. Fourth option

###### Explanation
Why C is correct. This is shown after the student answers.

---
```

### Question types

| Type | `type:` value | `correct:` format | Notes |
|------|--------------|-------------------|-------|
| Single choice | `single_choice` | `[b]` | Exactly one correct answer |
| Multiple choice | `multi_choice` | `[a, c]` | Two or more correct answers. State how many to select in the stem. |
| True/false | `true_false` | `[a]` or `[b]` | Options are always A. True / B. False |
| Sequence/ordering | `sequence` | `[b, d, a, c]` | The correct order of the option letters |

### Rules

- Question IDs must be unique within a file (e.g. `q001`, `q002`)
- Option letters are uppercase: `A.`, `B.`, `C.`, `D.`, `E.`
- The `correct:` value uses lowercase letters in a list: `[a]`, `[b, d]`
- The `type:` and `correct:` lines must immediately follow the `##### Question` header
- Every question should have an `###### Explanation` section
- Images use `![[filename.png]]` syntax (Obsidian-style)

## Content guidelines

When creating or editing quiz content in this repository:

1. **Original content only.** Never copy questions from exam dumps, brain dumps, official practice tests, or copyrighted sources. Write questions based on general knowledge of the topic.
2. **Always include the disclaimer** in frontmatter: `note: "Sample study questions — not affiliated with or sourced from official exams"`
3. **Accuracy matters.** Make sure correct answers are actually correct. Include clear explanations.
4. **Mix question types.** A good quiz uses a variety — single choice, multi choice, true/false, and sequence where appropriate.
5. **Aim for 15-20 questions per file.** Enough to be useful, not so many that quality drops.

## File organisation

```
azure/az-900-cloud-concepts.md      # {vendor}/{exam-code}-{topic}.md
aws/cloud-practitioner.md
comptia/a-plus-core-1.md
templates/blank-quiz.md              # Empty starter template
```

- Filenames: lowercase, hyphens, include exam code where applicable
- Each vendor folder has a `README.md` listing available quizzes
- The `templates/` folder contains a blank starter with one example of each question type

## When helping users

- If asked to create a quiz, follow the format exactly — whoiswilson.app parses these files and will reject malformed content
- If asked to add questions to an existing file, match the existing ID numbering pattern (e.g. if the last question is q020, start at q021)
- If asked to review a quiz, check for: correct format, accurate answers, clear explanations, and the disclaimer in frontmatter
- Suggest running the file through the whoiswilson.app editor preview to validate before committing
