# Biology Concept Tutor

A conversational Codex Skill that helps biology students understand unfamiliar concepts in research papers and textbooks, then return to their reading.

**Version: v0.2 — Initial Public Beta.** This is an early public testing version, intended for feedback and collaboration.

## Who it is for

Undergraduate and graduate biology students, researchers encountering unfamiliar topics, and readers rebuilding prerequisite knowledge after a break.

## The problem

A definition can introduce more unfamiliar terms than it explains. This Skill guides Codex to identify the smallest knowledge gap blocking the current passage, teach it in manageable steps, and check whether the reader can use the idea independently.

## Core teaching principles

- Diagnose existing understanding and reuse knowledge already demonstrated.
- Select only prerequisites needed for the current reading goal.
- Teach one necessary gap at a time; avoid unnecessary prerequisite recursion.
- Ask one focused question at a time and wait for the student's actual answer.
- Correct specific misconceptions without restarting the whole lesson.
- Distinguish established background, observations, interpretations, and hypotheses.
- Return to the original passage after explaining the concept.
- Check independent explanation and application, then stop when the current goal is met.
- Respect requests to pause or skip checks; mark untested understanding honestly.

## Supported uses

- Understanding an unfamiliar term in a textbook or research passage.
- Connecting a concept to a specific Results statement or figure interpretation task when the relevant material is available.
- Separating an experimental intervention from its observed outcome.
- Repairing misconceptions, including confusion between DNA deletion and RNA splicing.
- Learning across biology topics without applying the same prerequisite chain everywhere.

## Limitations and non-goals

This is an instruction-only Skill, not a standalone application or a complete biology course. It does not provide whole-paper summaries by default, write submission-ready homework, or maintain student profiles across chats.

Model responses can be scientifically wrong or fail to follow the teaching rules. Missing paper context, inaccessible sources, and unavailable verification tools limit what can be established. Local understanding checks do not prove lasting mastery.

The maintainer reports that v0.2 passed three formal human-interaction tests covering Results interpretation, figure interpretation, and cross-topic concept learning. These are promising early checks, not large-scale educational validation. Private transcripts and internal evaluation reports are not distributed, and this public packaging has not undergone a new interaction study.

Compatibility with other AI assistants has not been verified.

### Language

The preserved v0.2 teaching instructions and reference files are in Simplified Chinese. Teaching defaults to Simplified Chinese; explicitly request English or another language to change the interaction language. This public README and feedback template are in English. English-language teaching quality has not been separately established.

## Install in Codex

Use a current Codex installation that supports local Skills. No additional software packages or API keys are required by this Skill itself; normal Codex access is still required.

1. Download this repository using GitHub's **Code → Download ZIP**, or download the source archive for the v0.2 release.
2. Extract it and rename the extracted folder to `biology-concept-tutor`.
3. Put the folder in **one** of the following locations:

| Scope | Skill folder |
| --- | --- |
| One project | `<your-project>/.agents/skills/biology-concept-tutor/` |
| Your user account | `~/.agents/skills/biology-concept-tutor/` (under your home directory) |

The resulting layout must include:

```text
.agents/skills/biology-concept-tutor/
├── SKILL.md
└── references/
    ├── examples-and-edge-cases.md
    └── manual-evaluation.md
```

Keep the repository's license and accompanying documentation with your copy. Avoid an extra nested repository folder between `biology-concept-tutor/` and `SKILL.md`. Opening the downloaded repository by itself does not install its root-level Skill.

For a project installation, open that project in Codex. Codex detects changes automatically; restart it if the Skill does not appear. In the CLI or IDE extension, use `/skills` or type `$` to locate it.

These locations and discovery steps follow the [official Codex Skill documentation](https://learn.chatgpt.com/docs/build-skills), checked on October 8, 2026. This beta is distributed as a folder for manual local installation.

## Invoke the Skill

Send a prompt such as:

```text
$biology-concept-tutor
Please tutor me in English, asking one question at a time.
I am reading about introns. I know DNA stores information, but I do not
understand RNA. Help me understand the concept and return to my passage.
```

Add the relevant passage or describe the figure, with its source location, when you are permitted to share it. Without source context, the tutor can explain general concepts but should not invent paper-specific findings.

## Example interaction

**Illustrative, fictional dialogue; not a real student transcript or a quotation from a paper.** Each tutor turn below follows a separate student reply.

**Student:** $biology-concept-tutor Please tutor me in English. This fictional exercise says, “We deleted intron I from genomic DNA and compared growth with the parent strain.” I know DNA stores information, but what is RNA?

**Tutor:** A cell can use a stretch of DNA as a template to make a separate RNA molecule with a corresponding sequence. For this example, think of a source and a working copy; the molecules are distinct. If a piece is removed from one RNA copy, does the DNA template necessarily lose that piece?

**Student:** No. Changing the separate copy does not change its source.

**Tutor:** Right. In this example, an intron is a segment included in the initial RNA and removed during RNA splicing; surrounding retained segments are joined. Ordinary splicing changes RNA. Your exercise describes a different operation: deleting a sequence from DNA. How would that deletion affect new RNA made from the edited template?

**Student:** New RNA could not copy the deleted sequence. Splicing instead removes it from RNA after it has been copied.

**Tutor:** You have distinguished the two operations. In the exercise, comparing growth is a way to investigate the deletion's consequences. What does the sentence let you conclude about whether growth changed?

**Student:** It only says they compared growth. It does not give a result.

**Tutor:** Exactly. Return to the passage with those distinctions: the intervention changes DNA, and the growth comparison needs a reported result before you can describe its outcome.

## Report bugs or teaching failures

Open a GitHub Issue using the **Bug or teaching failure** template. Describe the task, expected and actual behavior, prerequisite choices, explanation length, scientific calibration, return to reading, and stopping point. Include the Skill version, Codex client, and model when known.

Prefer a minimal fictional reproduction and a paraphrase of the failure. Do not upload private conversations, unpublished research, personal information, credentials, or copyrighted paper content without permission. For scientific errors, a public source link and location are more useful than a copied paper.

## Contribute

Issues and focused pull requests are welcome. Explain the problem and the observable improvement; discuss changes to teaching behavior before proposing a patch. Keep v0.2 behavior intact when making packaging or documentation fixes.

Submit only material you created or are authorized to redistribute under the project's license, and identify any third-party content and its license. Keep private test records outside the repository.

The [examples and edge cases](references/examples-and-edge-cases.md) explain existing decisions. The [manual evaluation guide](references/manual-evaluation.md) contains reusable synthetic cases, not private evaluation results. It is for reviewers, not ordinary tutoring. Its opening project-local installation description reflects the original development setup; use the installation instructions above for this distribution. Its Chinese test prompts also preserve the original testing context.

When reporting a manual test, distinguish file validation, scripted rehearsal, and actual human interaction. Report failures and unresolved understanding without claiming broad learning effectiveness.

## Version and license

This package preserves the v0.2 teaching files unchanged. The planned release title is **v0.2 — Initial Public Beta**. No v0.3 teaching changes are included.

Licensed under the [MIT License](LICENSE). Copyright (c) 2026 takeanothernap-maker. You may use, copy, modify, and redistribute this material under its terms, including retaining the copyright and license notice. The material is provided without warranty.
