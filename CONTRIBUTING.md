# Contributing

Thanks for considering a contribution! Every quiz you share helps someone studying for an exam.

## Ground rules

1. **Original content only.** Do not copy questions from exam dumps, brain dumps, official practice tests, or any copyrighted source. Write questions in your own words based on your understanding of the topic.
2. **Sample, not substitute.** These are study aids to help people get started — not a replacement for proper exam preparation.
3. **Be accurate.** Make sure your correct answers are actually correct. Include explanations where possible.

## Quiz format

Quizzes are markdown files with a YAML header. Here's the structure:

```markdown
---
title: "Your Quiz Title"
tags: [topic, certification]
note: "Sample study questions — not affiliated with or sourced from official exams"
---

##### Question q001
type: single_choice
correct: [b]

Your question text here.

A. First option
B. Second option
C. Third option
D. Fourth option

###### Explanation
Why B is correct.

---
```

**Supported question types:** `single_choice`, `multi_choice`, `true_false`, `sequence`

For the full format guide, see [whoiswilson.com/howto](https://whoiswilson.com/howto).

A blank template is available at [templates/blank-quiz.md](templates/blank-quiz.md).

## How to contribute

1. Fork this repository
2. Create your quiz file in the appropriate folder (e.g. `azure/`, `aws/`)
3. Follow the naming convention: `{exam-code}-{topic}.md` — e.g. `az-900-cloud-concepts.md`
4. Include the `note` field in your frontmatter (see above)
5. Submit a pull request

**If a folder for your topic doesn't exist yet**, create one and include a brief `README.md` inside it listing the available quizzes.

## Review process

A maintainer will review your PR for:
- Format compliance (parses correctly on whoiswilson.app)
- Originality (no copied content)
- Accuracy (correct answers are correct)

We may suggest edits before merging. Don't take it personally — we want every quiz to be useful.

## Naming convention

| File | Contents |
|------|----------|
| `az-900-fundamentals.md` | Broad coverage of AZ-900 topics |
| `az-900-cloud-concepts.md` | Focused on the cloud concepts domain |
| `az-104-identity.md` | AZ-104 identity and governance questions |

Keep filenames lowercase, use hyphens, and include the exam code where applicable.

## Questions?

Open an issue on [github.com/whoiswilson-com/sample-quizzes](https://github.com/whoiswilson-com/sample-quizzes) or reach out via [whoiswilson.com](https://whoiswilson.com).
