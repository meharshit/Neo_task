# Technical Writer case study: Tracks

## Contents

| Part | File | What it is |
|---|---|---|
| 1 | `part-1-clarifications.md` | The nine questions that decide whether the docs are correct, each with who to ask and the assumption I took, plus a short list of smaller assumptions |
| 2 | `part-2/1-tracks-overview.mdx` | Feature overview for someone using Tracks for the first time: prerequisites, roles and access, how it works, use cases, the features it offers, reference tables, best practices, and next steps |
| 2 | `part-2/2-how-to-run-a-task-through-several-workstreams.mdx` | How-to guide for one specific task, from turning on Tracks to completing the task |
| 2 | `part-2/3-release-note-tracks.mdx` | Release notes in five sections: What's new, What's enhanced, What's changed, Deprecated, and Removed |
| 2 | `part-2/glossary.mdx` | Every term the docs use, each one shown as a tooltip on first mention |
| 3 | `part-3/writing-docs-from-prds/SKILL.md` | The reusable skill, in one file |
| 3 | `part-3/writing-docs-from-prds.skill` | The same skill, packaged so it can be saved straight into Claude |


## Important points

- **Check the spec first.** I reviewed the objects, states, actions, permissions, and lifecycle events and compared them across the PRD. I found one important conflict around turning off Tracks and whether that means hiding or deleting it.

- **Keep the questions focused.** Part 1 has nine questions that need an answer from the PM or engineer. I listed the lower-risk assumptions separately so they can be confirmed quickly.

- **Be careful with user data.** Where the PRD was unclear about actions that could remove data, the docs take the safer approach and call out the risk.

- **Use Neo's style.** Since Tasket is a Neo product, the docs use Neo's product names and terminology, with short and direct explanations. Examples cover different functions instead of focusing on one workflow.

- **Give each document one purpose.** The overview explains the feature and links to the reference. The how-to walks through a specific task. The release notes explain what changed. Each document links to the others instead of repeating the same content.

- **Turn user stories into use cases.** Each user story maps to a use case. Edge cases become table rows, warnings, limitations, or troubleshooting items where needed.

- **Keep it ready for Mintlify.** The docs include the required frontmatter, callouts, and glossary links. The feature overview explains what Tracks does, while the how-to contains the step-by-step instructions.

- **Keep the skill simple.** The skill uses one `SKILL.md` file so it can work across LLM tools and be easy to update. It first looks at the company and feature, then creates the questions log, glossary, overview, how-to, and release notes, followed by a final checklist. If we build a larger skill library later, it would make more sense to split this into a small main file with separate reference files that are loaded only when needed.