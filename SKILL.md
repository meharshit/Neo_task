---
name: writing-docs-from-prds
description: Turns a product requirements document (PRD), spec, or feature brief into documentation drafts in the company's own style. Produces the few questions that decide whether the docs are correct, with the assumption taken for each, a glossary, a feature overview, a how-to guide for one task, and release notes split into What's new, What's enhanced, What's changed, Deprecated, and Removed. Adapts to any feature type, including UI features, APIs, SDKs, settings, integrations, behavior changes, and deprecations. Writes Google developer documentation style as Mintlify MDX. Use this skill whenever the user shares a PRD, spec, design doc, epic, or ticket and asks for docs, a feature page, user guide, help article, how-to, release notes, a changelog, "what's new" copy, or questions to ask the PM, even if they ask for only one of these.
---

# Writing docs from PRDs

A PRD is usually a working draft. It contradicts itself, skips permissions, and leaves numbers undefined. This skill reads it like a technical writer in their first week: find the gaps, ask about the ones that matter, take a sensible assumption for each, and then write. Most PRDs change something that's already documented, so the skill updates existing pages wherever it can, and writes only what each feature actually needs.

## How this file is organized

| Section | Edit it to change |
|---|---|
| 1. Settings | Author, version, format, outputs, file names, risk policy |
| 2. Workflow | The order of work |
| 3. Company style | Product names, terms, voice, and punctuation for a company |
| 4. Adapting to the PRD and existing docs | Which sections a feature gets, and how existing pages are updated |
| 5. Questions log | What to ask the PM and developers, and how |
| 6. Writing rules | Any sentence-level rule, frontmatter, callouts |
| 7. Glossary and tooltips | Definitions and tooltips |
| 8. Feature overview | The overview's structure |
| 9. How-to guide | The how-to's structure |
| 10. Release notes | The release notes' structure |
| 11. Final checklist | What gets checked before handover |

If two sections disagree, Settings wins, then the section for that document type wins over the general writing rules.

---

## 1. Settings

If the user asks for something different, follow the user.

| Setting | Default |
|---|---|
| Company style | Google style, with the company profile from section 3 on top. Current profile: Neo, maker of Tasket |
| Readers | Both technical and non-technical. Plain explanation first, technical detail after it |
| Format | Mintlify MDX, with the frontmatter in section 6, and no H1 |
| Author | Harshit Satyaseel |
| Version | `[Version]` until the PM confirms it. Deprecation dates use `[Month Year]` until confirmed |
| Sidebar tag | `tag: "New"` on every page about a new feature. `"Beta"` or `"Updated"` when they apply |
| Callouts | `<Note>`, `<Info>`, `<Tip>`, `<Warning>` |
| Tooltips | `<Tooltip>` on the first mention of each glossary term on a page |
| Em dashes and en dashes | Never. Use commas, colons, or two sentences |
| Existing docs | Ask for them before drafting. If they exist, update them instead of writing new pages that repeat them |
| Outputs | Questions log, glossary, feature overview, how-to guide, release notes. If the user asks for one, produce that one plus the questions log and any glossary terms it uses |
| File names | `1-questions.md`, `2-<feature>-overview.mdx`, `3-how-to-<task>.mdx`, `4-release-notes.mdx`, `glossary.mdx` |
| Release notes header | Title `[Month Year] release notes`, then **Version:** and **Released:** lines |
| When risky behavior is unclear | Document the reading that protects user data, and log it |
| Assumptions inside drafts | Not marked. The questions log holds them |
| Preview copies | If the reader can't open Mintlify, also give `.md` copies: callouts as blockquotes with a bold label, tooltips as links to the glossary, and Steps as a numbered list |

---

## 2. Workflow

Copy this checklist into your response and tick it off as you go:

```
Progress:
- [ ] 1. Read every source
- [ ] 2. Profile the PRD and the company
- [ ] 3. Build the fact sheet
- [ ] 4. Write the questions log
- [ ] 5. Plan each document
- [ ] 6. Draft
- [ ] 7. Check and fix
- [ ] 8. Hand over
```

**1. Read every source.** Read the PRD in full, then every supporting file: designs, tickets, user stories, and Slack threads. Then get the existing docs for the product: ask the user for files or links, or read them from a connected docs repo, Mintlify, Notion, or Confluence. If there are none, say so and treat everything as new. When sources disagree, newer decisions win, and labels in a design beat labels in prose. Note each disagreement for the questions log.

**2. Profile the PRD and the company.** Apply section 3 for the company and section 4 for the feature. Write a short profile before going further:

```
Company: <name, and the profile used>
Feature type(s): <UI feature, API, SDK, setting, integration, permissions, behavior change, deprecation, fix>
Features in this PRD: <one, or a list>
Readers and roles: <who uses it, each role's access, how technical they are>
Docs state: <new feature, change to a documented feature, or both>
Pages to create: <new pages, with the reason>
Pages to update: <existing pages the PRD changes>
Outputs: <which documents, and any to skip with the reason>
How-to task: <the one task the guide covers>
```

**3. Build the fact sheet.** List every term, prerequisite, role, object, state, action, permission, lifecycle event, edge case, limit, default, counter, UI label, and API surface. For each action, note where it is, who can do it, whether it works offline, whether it can be undone, and whether it asks for confirmation. Write "Not specified" wherever the sources are silent. This is working material, so show it only if the user asks.

**4. Write the questions log.** Follow section 5. Every gap becomes either a question or a listed assumption, so the drafts never wait on an answer.

**5. Plan each document.** For existing docs, build the change map in section 4. For new pages, decide which sections each one needs using the Include when table in section 8, and skip the rest. Decide the one task the how-to covers. Map each user story: its goal becomes a use case row and a how-to stage, and its edge cases become callouts, table rows, limitations, or troubleshooting entries. Classify each change into a release notes section using section 10. That's your call, not a question for the PM.

**6. Draft.** Write the glossary first, because every other document takes its definitions and tooltips from it. Then write the overview, the how-to, and the release notes, following sections 6 to 10. Use only facts from the fact sheet or assumptions from the log. When the PRD doesn't name a button, write a generic action, such as "Save the track" or "Confirm," because an invented label sends readers hunting for UI that doesn't exist.

**7. Check and fix.** Work through section 11 for every document. Fix what fails, and check again.

**8. Hand over.** Present the files. For each updated page, add a change summary: each section you changed, what changed, and why, so reviewers can check the diff quickly. In two or three sentences, name the questions where a wrong assumption would mislead readers most.

### Principles

When a case isn't covered, decide using these:

- **Accuracy beats polish.** A clean page with a wrong fact does more damage than a rough page with a logged question.
- **Protect user data.** If the docs say an action is safe and it isn't, users lose work. If they warn and it's safe, nobody is hurt.
- **One job for each document.** The overview explains, the how-to walks through one task, and the release notes say what changed. Each links to the others instead of repeating them.
- **Plain first, technical after.** Every section should make sense to a non-technical reader before it gives technical readers the detail they came for.
- **Update before you create.** A second page about the same feature splits readers and goes out of date. Change the page that already exists.
- **Write what the feature needs.** Every section has to earn its place. A short, complete page beats a long one padded to match a template.
- **Write for scanning.** Tables, short paragraphs, and descriptive headings get readers to their answer faster than long prose.

---

## 3. Company style

Google style is the base. The company's conventions sit on top: product names, terms, voice, and punctuation. Where the company has clearly decided something, follow the company. Where its sources disagree, follow Google and log a question.

### Build a profile for a new company

Read these sources, in order of authority: a brand or docs style guide from the user, existing docs or a help center, the product UI, the website, then careers pages and launch posts. Capture the following:

| Capture | Look for |
|---|---|
| Product names | Exact spelling and capitalization, and how products relate |
| Company and suite names | When to use the company name and when to use the product name |
| Core terms | The nouns used for objects and roles |
| Audience | Who the company sells to, so examples fit them |
| Voice | Sentence length, formality, how concrete the verbs are |
| Punctuation | Serial comma, hyphenation, number style |
| Slogans | Taglines to keep out of docs |
| Inconsistencies | Places where sources disagree, for the questions log |

Write it in the same shape as the Neo profile below. Define company products that the PRD mentions in passing, such as an AI assistant or a docs app, in the glossary.

### Neo profile

Sources: neo.work, Neo careers pages, and launch coverage, read October 2026. No public Neo docs or help center was found.

| Name | What it is | Rules |
|---|---|---|
| Neo | The company and its AI work platform | Use for the company and the suite, not as a product name inside Tasket docs |
| Tasket | Neo's work management platform, for every function | Always capitalized, with no article: "Tasket," not "the Tasket" |
| Friday | Neo's AI assistant, co-worker, and agent platform, built into Tasket, Studio, and Drive | A task's "Friday chat" is its conversation with Friday |
| Studio | Neo's app for docs, spreadsheets, and diagrams | "Studio documents" are Studio files attached to a task |
| Drive | Neo's file repository, shared by people and agents | Capitalize |
| Scribe | Neo's AI assistant for meetings | Capitalize |

- **Core terms:** teams, projects, tasks, guests, and agents. Neo describes teams as people from inside the organization plus guests from outside it. Write "organization" in docs, not "org," and "people and agents," not "humans and agents."
- **Audience:** every function, not only engineering. Use examples from marketing, hiring, operations, and content as well as engineering. Guests are common, so always say what guests can and can't do.
- **Voice:** short, confident sentences with concrete verbs that say what happens. Keep that concreteness within Google style.
- **Punctuation:** the site leaves out the serial comma, but launch posts use it. Use it, following Google. Write "more than 1,000," not "1000+."
- **Keep out of docs:** home page taglines, and words like "radically reimagined" or "AI-native" used as praise.

---

## 4. Adapting to the PRD and existing docs

Shape the documents to the feature in front of you. A PRD often has more than one type. Merge their sections, with the main type first.

| Feature type | Signals | Add to the overview | How-to task | Release notes section |
|---|---|---|---|---|
| UI feature | Screens, tabs, boards, buttons, flows | A section for each main surface with an actions table, statuses and transitions, how changes affect it | The main job, from setup to finish | What's new |
| API | Endpoints, request and response bodies, status codes, auth | Authentication, endpoints table, request and response examples, errors table, rate limits | Make the first successful call, with code | What's new. New fields in What's enhanced. Changed fields in What's changed, marked **Breaking** if code fails |
| SDK or library | Install, packages, versions, methods, events | Requirements and versions, install, configuration and methods tables | Install and complete the main integration, with code | What's new or What's enhanced, with the version in the heading |
| Setting | A toggle, a default, who can change it | Where it is, the default, who can change it, what it affects | Turn it on and configure it. Often short enough to skip a separate how-to | What's enhanced |
| Integration | A third-party product, syncing data | Requirements on both sides, what syncs, how often, what happens on disconnect | Connect it and confirm data flows | What's new |
| Permissions | Roles, access levels | Expand Roles and access | Give or limit access for a role | What's enhanced or What's changed |
| Behavior change | An existing feature that now works differently | A "What's different" section, with before and after and who's affected | Adjust to the change, if readers must act | What's changed |
| Deprecation or removal | Something going away, a replacement, a date | No overview. A short page on what's going away, why, the timeline, and the replacement | Migrate to the replacement | Deprecated or Removed |
| Fix or improvement | Performance, reliability, bug fixes | None | None | What's enhanced, or What's changed if behavior differs |

The following table covers different PRD shapes:

| The PRD | What to do |
|---|---|
| Has no user stories | Build use cases from the problem statement and goals |
| Has no permissions section | Ask who can do each action. Assume the most restrictive reasonable reading for destructive ones |
| Has designs | Take UI labels and locations from the designs |
| Has tickets or threads | Treat newer decisions as overriding the PRD |
| Covers several separate features | Write one overview and one how-to for each, and one release notes page for all |
| Mentions future work | Leave it out of the documents |

Match length to the feature. A small setting might need a 300-word overview with no separate how-to. A large UI feature might need a 1,500-word overview and a seven-stage how-to.

### Decide what to create and what to update

The following table shows what to do for each kind of change:

| The PRD | What to do |
|---|---|
| Adds a feature with its own screen or workflow | Create an overview and a how-to. Add links to them from related existing pages |
| Changes a documented feature | Update its existing pages. Don't write a new overview |
| Adds a small capability to a documented feature | Add a section or a few rows to the existing page |
| Adds a setting or option | Add it to the page that documents that area |
| Removes or deprecates something | Update or remove the pages that describe it, and point readers to the replacement |
| Any change | Write new release notes. They're always a new page |

### Build a change map

Before editing, list every place the PRD touches. Search the existing docs for the old behavior, its UI labels, and its terms, because the same fact often appears on several pages: the overview, a how-to, a FAQ, and the glossary.

| Page | Section | What changes | Action |
|---|---|---|---|
| <Existing page> | <Section> | <Old behavior, then new behavior> | Update, add, or remove |

### Update an existing page

- Keep the page's structure, headings, voice, and terms. Readers and search engines already know them.
- Change only what the PRD changes. Leave unaffected sections word for word, so the diff stays small and easy to review.
- Fix every page that states the old behavior, not just the main one.
- Update links, the glossary, and navigation for anything renamed, added, or removed.
- Update `lastUpdated`, `version`, and `readTime`, and set `tag: "Updated"` when the change is significant.
- If the existing docs contradict the PRD, or look outdated, log it as a question instead of guessing which is right.

### Stay consistent without copying

Consistency helps readers move between pages. Copying makes every page sound the same and hides what's specific to each feature.

| Keep consistent across features | Write fresh for each feature |
|---|---|
| Section names for the same purpose, such as Prerequisites or Next steps | Every example, scenario, and use case, taken from this PRD |
| Terms and product names | Sentences, including openings and Why it matters lines |
| Patterns: how procedures, tables, and callouts are written | Which sections appear, and how long each one is |
| Frontmatter fields and release notes sections | The number of use cases, best practices, and callouts |

If the existing docs follow a pattern that differs from this skill, such as a different heading style, follow the existing docs on pages you update, and note the difference in the handover.

A quick test: if you could swap in another feature's name and a sentence would still be true, it's too generic. Rewrite it with a fact from this PRD.

---

## 5. Questions log

The questions log is what you'd send a busy PM or engineer before publishing. It holds only the questions that decide whether the docs are correct, accurate, and complete. Everything else you assume, and list briefly.

### Which questions to ask

For each gap in the fact sheet, ask yourself: if my assumption is wrong, would the docs mislead a reader? Ask it only if the answer is yes and you can't work it out from the PRD. That usually leaves six to ten questions. Make a gap a question if it's one of the following:

1. A contradiction, where the two readings would make the docs say different things. This includes the PRD contradicting the existing docs.
1. A risk to user data, such as an action that might be permanent or a change that might be lost.
1. A missing permission for an action that matters, especially a destructive one.
1. A number users act on, such as a counter or a limit, with no definition.
1. A gap that blocks a whole section, such as an action with no described result.
1. The version number, if the PRD doesn't give it, and the removal date for anything deprecated. These are the only release notes questions.

Put defaults, naming rules, limits, confirmation dialogs, and wording in "Smaller details I assumed." Leave out what you decide yourself: typos, release notes sections, and style choices.

Combine related gaps into one question. Ask for designs or a build once, instead of asking where each button is. Write like a colleague, in one to three plain sentences.

### Format

```markdown
# Questions before writing the <Feature> docs

These are the questions that decide whether the <Feature> docs are correct. For each one, I've noted who can answer it and the assumption I used, so the drafts are ready now. If an answer is different, I'll update the docs.

The following questions are in order of importance:

| # | Question | Ask | Assumption I took |
|---|---|---|---|
| 1 | <Question> | PM | <Assumption> |

## Smaller details I assumed

These don't need a meeting. If any of them is wrong, a quick reply is enough:

- <Assumption, in one sentence.>
```

Order questions by how badly a wrong assumption would mislead readers. Write **PM** for behavior, permissions, and the version, and **Dev** for how it's built, limits, sync, and designs. Keep the assumptions list to about eight bullets.

- Good: "Who can delete a track? It's the only permanent track action, and it's missing from the permissions table."
- Not this: three rows asking where the switch, the Rename action, and the Delete action are. Ask for the designs once.

---

## 6. Writing rules

These follow the Google developer documentation style guide, with the company profile on top. They apply to every document except the questions log.

### Frontmatter

Every MDX file starts with this block:

```yaml
---
title: "<Page title, in sentence case>"
description: "<One sentence on what the page lets the reader do>"
product: "<Product>"
feature: "<Feature>"
contentType: "<Overview | How-to | Release notes | Glossary>"
audience: ["<Role>", "<Role>"]
version: "[Version]"
author: "<Author from Settings>"
lastUpdated: "<YYYY-MM-DD>"
readTime: "<N> min"
tag: "New"
keywords: ["<Search term>", "<Search term>"]
---
```

- Keep `description` to one sentence. It shows in search results and link previews.
- Take `audience` from the PRD's roles.
- Use `tag`, singular. Mintlify shows it as a sidebar badge. Remove `"New"` after the next release, and leave `tag` out when there's nothing to flag.
- Use three to six `keywords` that readers would type into search, including UI names.
- Calculate `readTime` after the last edit: count the words in the body, leaving out code blocks and component tags, divide by 200, and round up. Set `lastUpdated` to today.

### Readers

Explain in plain words first, then add technical detail such as sync rules, limits, and field names. Define a technical term in a short clause the first time it appears. Put reference detail in tables, so technical readers can scan and others can skip.

### Openings

1. In the first sentence, say what the feature is and what it lets the reader do, with a familiar example: "Tracks is a Tasket feature that lets your team move one task through several workstreams at the same time, such as Spec, Design, and QA."
1. In the second sentence, explain the core idea and introduce the main term.
1. Follow with a short "For example" paragraph built on the PRD's scenario, ending with the main benefit.

Don't open with "This document describes," "This page explains," "Welcome," or casual openers such as "Take a ..." or "Imagine ...". For how-tos and release note items, one sentence is enough: "<Feature> lets you <do X>."

### Voice and words

Address the reader as "you." Use present tense, active voice, and contractions. Spell out zero through nine, and use numerals for 10 and up and for counts shown in the UI. Use "they" for one person of unknown gender. The following table lists words to avoid:

| Avoid | Use instead |
|---|---|
| will (for product behavior) | Present tense |
| e.g., i.e., etc. | for example, that is, and so on |
| in order to, utilize, via, allows you to | to, use, through, lets you |
| enable, disable (for a switch) | turn on, turn off |
| please, simply, just, easy, quick | Leave it out |
| powerful, seamless, robust, unlock | Say what it does |
| above, below | preceding, following |
| sanity check, kill | quick check, stop |

### Headings

Use sentence case. Start task headings with a verb: "Add a track." For concept headings, name the thing and what the section says about it: "Track statuses and how they change," not "Statuses." Avoid generic headings such as "Overview," "Details," "How it works," or "More information." End overviews and how-tos with "Next steps," not "What's next."

### Lists, tables, and procedures

- Introduce every list and table with a full sentence that ends in a colon: "The following table describes each status:"
- Use numbered lists for steps and bulleted lists for everything else. Use tables for anything a reader looks up.
- Introduce each procedure with "To <goal>, follow these steps:" and write one action per step, numbering every step `1.`
- Put the location before the action ("In the **Tracks** tab, click **Add track**") and the condition before the instruction ("If the task is Done, click **Mark Pending**").
- Start optional steps with "Optional:". After the steps, state the result.

### UI text

Bold UI labels exactly as they appear, such as **Settings**. Don't bold status names in running text. Use "click" for generic interaction. If a button shares its name with a common verb, such as **Select**, use that word only for the button. Use code font for values the reader types, file names, and code.

### Callouts

The following table describes each callout type:

| Component | Use it for |
|---|---|
| `<Note>` | Behavior the reader might not expect |
| `<Info>` | Helpful context that isn't needed to finish |
| `<Tip>` | A shortcut or an extra option |
| `<Warning>` | Data loss, an action that can't be undone, or a security or privacy risk |

Give every irreversible action and every silent data loss a `<Warning>`, in every document where it appears. In a how-to, put the `<Warning>` before the step it applies to, so readers see it in time. Keep callouts to one to three sentences, with no headings or lists inside. Use at most one in each section, never two in a row, and never put a required step in one, because readers skip callouts.

### Code samples

For APIs and SDKs, show a complete, runnable example for the main task: `curl` for APIs, plus the languages the PRD names. Use realistic values and clear placeholders, such as `YOUR_API_KEY`, and explain each placeholder after the block. Show the response after each request, and tag every code block with its language.

### Links and tone

Write "For more information, see [Page title](link)." In release notes, write "Learn more in [Page title](link)." Use the page or section title as link text. Vary sentence length, prefer a concrete example from the PRD over a general claim, and don't end a section by repeating its point.

---

## 7. Glossary and tooltips

Every term gets one definition, in the glossary. Pages show it in a tooltip on first mention, so there's no Key terms section in any document.

**Build the glossary.** If the user gives you a glossary, use its definitions exactly, add only missing terms, and deliver the full updated file with `tag: "Updated"`. Otherwise, create `glossary.mdx`. Include new feature terms, existing product terms the docs rely on, such as role names, and company products the PRD mentions in passing. Give each term its own `##` heading, in alphabetical order, so pages can link to `./glossary#<term>`.

**Write definitions** as a noun phrase, in one or two plain sentences, with the one fact that matters most. Take every fact from the PRD or the company profile.

- Good: "A workstream in a project, such as Spec, Design, or QA. Each track appears as a column on the Tracks board and exists only in the project where it was created."
- Not this: "Refers to a track, which is a feature used for tracking work across workstreams in a seamless way."

**Add tooltips** on the first mention of each glossary term on a page, in running text or lists, not in headings or table cells:

```mdx
<Tooltip tip="A workstream in a project, such as Spec, Design, or QA, shown as a column on the Tracks board." cta="See the glossary" href="./glossary#track">track</Tooltip>
```

Keep `tip` under about 25 words, with no double quotes inside. Link the glossary in the overview's Next steps.

---

## 8. Feature overview

The overview explains what the feature is, who uses it, what it can do, and how it behaves. It never contains numbered procedures, because those belong in the how-to. Write one only for a feature with its own screen or workflow. For a change to a documented feature, update its existing overview instead (section 4).

The template lists every section an overview can have. It's a menu, not a form. Include a section only when its condition in the following table is true, and skip it otherwise:

| Section | Include when | If you skip it |
|---|---|---|
| Opening and How it works | Always | |
| Prerequisites | Something must be set up, turned on, installed, or paid for first | Say who can use it in the opening |
| Roles and access | What people can do differs by role | One sentence on who can use it |
| Use cases | The feature serves several distinct situations | Leave it out. Don't invent cases to fill a table |
| Features | Always. One `###` subsection for each capability | |
| Feature-type sections | Section 4 lists them for this type | |
| How changes affect | Actions interact, such as closing, moving, or deleting | |
| Offline availability | The product works offline and this feature behaves differently offline | |
| What's different | The feature replaces or changes existing behavior | |
| Limitations | The PRD states limits, or edge cases that block readers | |
| Best practices | The PRD gives grounds for at least three specific practices | Leave it out rather than writing generic advice |
| Next steps | Always | |

```mdx
---
<Frontmatter from section 6, with contentType: "Overview">
---

<Feature> is a <product> feature that lets you <main thing the reader can do>, such as <familiar example>. <The core idea, introducing the main term with a tooltip.>

For example, <the PRD's scenario>. With <feature>, <what happens, and the main benefit>.

## Prerequisites

To use <feature>, you need the following:

- <Access or role.>
- <Anything that has to be turned on or configured first, and who can do it.>

## Roles and access

<Who uses the feature.> The following table describes each role:

| Role | Who they are | What they do with <feature> |
|---|---|---|

The following table lists who can perform each action:

| Action | <Role> | <Role> | <Role> |
|---|---|---|---|

## How <objects> move through <feature>

<Two to four short paragraphs on the model, the main objects, and how they relate.>

<Note>
<The behavior most likely to surprise a new reader.>
</Note>

## Use cases

Teams use <feature> when <situation>. The following table lists common scenarios:

| Use case | Example | How <feature> helps |
|---|---|---|

## <Feature> features

<Feature> gives <the reader> the following capabilities. Each one is described in more detail later on this page.

### <Capability, as a noun phrase>

<What it does, in one or two sentences. Who can use it, if access is limited. The key rule or edge case. Where it is in the UI, named in bold.>

To <main task> step by step, see [<How-to title>](link).

<Sections for the feature type from section 4, with descriptive headings.>

## Limitations

<Feature> has the following limitations:

## Best practices

The following practices <outcome>:

- **<Imperative practice.>** <Why, tied to a rule in the PRD.>

## Next steps

- To <main task>, see [<How-to title>](link).
- To look up any term, see the [<product> glossary](./glossary).
```

Guidance for the sections:

- **Prerequisites:** list access, roles, settings that must be on, installs, plans, versions, or connections. For each one that needs setup, say who can do it. Readers who hit a missing prerequisite assume the feature is broken.
- **Roles and access:** start with a role table, then a permissions table with one row for each action, one column for each role, and "Yes" or "No" in each cell, plus a condition where access depends on something. Use one sentence instead if there's only one role.
- **Use cases:** a table of scenarios, written the way Stripe and Google do. Use as many rows as the feature has real situations, usually two to six. Name each after a kind of work, not a button, and write the benefit as an outcome. Base each row on a user story, and add one or two from other kinds of teams. Leave out steps and edge cases.
- **Features:** describe what readers can do, not how to do it. Give each capability a `###` noun-phrase heading, such as "Bulk start" or "Track management," and one short paragraph: what it does, who can use it, the key rule, and where it is in the UI. Add a `<Warning>` for anything irreversible. Don't write numbered steps. Procedures belong in the how-to, so end the section with a link to it.
- **Reference sections:** put statuses, transitions, actions by location, effects of changes, and offline availability in tables. Define every counter. Add a `<Warning>` after any table with an irreversible change.
- **Best practices:** three to eight bullets, after Limitations. Ground each in a PRD fact: an irreversible action, a limit, how a counter works, a default, or an edge case. Address a role when only one applies.
  - Good: "**Start a task only on the tracks that are working on it.** The pill counts Done tracks out of the tracks the task is on."
  - Not this: "**Use Tracks regularly.** Tracks works best when your team uses it consistently."

---

## 9. How-to guide

A how-to takes a reader with one specific task from start to finish. Choose the task the user names. Otherwise, choose the main job the feature exists for, and name it as a goal starting with a verb: "Run a task through several workstreams." Leave out tasks that aren't part of this goal.

```mdx
---
<Frontmatter from section 6, with contentType: "How-to">
---

<Feature> lets you <goal>. This guide takes you through <stage>, <stage>, and <stage>.

To learn how <feature> works first, see [<Feature> overview](link).

## Before you begin

- Make sure that <access, role, or required state>.

<Warning>
<Anything along the way that could lose the reader's work.>
</Warning>

## <Verb> <first stage>

<When to do this stage.> If <already done>, skip to [<next stage>](#anchor).

To <goal of this stage>, follow these steps:

1. <Location, then action.>

<What the reader sees now.>

### Optional: <Shortcut, such as a bulk action>

## Troubleshoot

The following are common issues and how to resolve them.

**<Symptom, in the reader's words.>**
<Cause.> <Fix.>

## Next steps

- To <related goal>, see [<Page title>](link).
```

Make each section one stage, in the order the reader does them, and let readers skip stages they've done. Add an Optional subsection, a `<Warning>`, or a Troubleshoot entry only where the PRD gives a real shortcut, risk, or problem. A short how-to with no Troubleshoot section is fine. If the change only affects an existing task, update that task's how-to instead of writing a new one. Keep explanation to one or two sentences in each section. Turn edge cases that could block the reader into troubleshooting entries. For API and SDK tasks, add credentials and versions to Before you begin, give each call its own stage with a code block and its response, and end with a Verify stage that shows how to confirm it worked.

---

## 10. Release notes

Release notes tell existing users what changed, in a form they can scan in a minute. Unlike the overview, their structure is fixed on purpose, so readers know where to look each release. Use these five sections, in this order, and keep every heading even when it's empty:

| Section | What goes in it |
|---|---|
| What's new | A feature that didn't exist before |
| What's enhanced | An existing feature that gains something, with everything it did before still the same |
| What's changed | An existing feature that now works differently, so readers might need to adjust |
| Deprecated | A feature that still works but is going away |
| Removed | A feature that no longer works |

**Choose the section** by asking, in order, and stopping at the first yes: Did it exist before? If not, What's new. Is it gone? Removed. Is it going away later? Deprecated. Does it now work differently? What's changed. Otherwise, What's enhanced. If an item is both enhanced and changed, put it in What's changed.

**Each item** has a heading with the name readers see (plus the version, for SDKs), an explanation line, two to five one-fact bullets, a `**Why it matters:**` line about the reader's benefit, a `<Warning>` or `<Note>` if needed, and `Learn more in [Page title](link).` The following table shows the explanation line and bullets for each section:

| Section | Explanation line | Bullets |
|---|---|---|
| What's new | "<Feature> lets you <do X>." | How it works, defaults, who can use it |
| What's enhanced | "<Feature> now <new capability>, so you can <benefit>." | What's added, and what still works as before |
| What's changed | "<Feature> now <new behavior>." | **Who's affected**, **What happens now**, **What you need to do** |
| Deprecated | "<Feature> is deprecated and will be removed in <Month Year>." | **Still works until**, **Use instead**, **What you need to do** |
| Removed | "<Feature> is removed as of <Month Year>." | **What no longer works**, **Use instead**, **What you need to do** |

For API changes that break existing code, start the heading with **Breaking:** and put the item first in What's changed. For an empty section, write one line, such as "Nothing is deprecated in this release."

```mdx
---
<Frontmatter from section 6, with contentType: "Release notes">
---

**Version:** [Version]

**Released:** [Release date]

<One or two sentences naming the biggest change and the sections it touches.>

## What's new

### <Feature name>

<Feature> lets you <what the reader can do>.

- <How it works.>
- <A default, rule, or key behavior.>

**Why it matters:** <The benefit to the reader.>

Learn more in [<Page title>](link).

## What's enhanced

## What's changed

## Deprecated

## Removed
```

Don't include procedures or future work. A deprecation with a removal date isn't future work.

---

## 11. Final checklist

Check every document before handing it over.

**All documents**

- [ ] Every fact comes from a source or from an assumption in the questions log. No invented labels, limits, or features.
- [ ] Product names and terms match the company profile, and terminology matches across documents.
- [ ] No em dashes or en dashes, no words from the "Avoid" table, and no "above" or "below."
- [ ] Every list and table has an intro sentence ending in a colon, and every procedure starts with "To <goal>, follow these steps:"
- [ ] Callouts use the four components, at most one in each section, and every irreversible action and silent data loss has a `<Warning>`.
- [ ] Each glossary term has a tooltip on its first mention on each page, linking to an existing glossary heading.
- [ ] MDX files have every frontmatter field, no `tags` field, a calculated `readTime`, and no H1.
- [ ] Links use page or section titles as link text, and every anchor exists.

**Updates to existing docs**

- [ ] Every page that states the changed behavior is updated, found by searching for old labels and terms.
- [ ] Unaffected sections are unchanged, word for word.
- [ ] The page keeps its existing structure, headings, and voice.
- [ ] Links, the glossary, navigation, and frontmatter are updated, with `tag: "Updated"` for significant changes.
- [ ] Each updated page has a change summary in the handover.

**Fresh, not copied**

- [ ] Every example and use case comes from this PRD, and no sentence would still be true with another feature's name swapped in.

**Questions log**

- [ ] Six to ten questions in order of importance, each one something that would make the docs wrong.
- [ ] Related gaps are combined, and UI locations are one request for designs.
- [ ] Low-risk assumptions are listed as one-line bullets.

**Glossary**

- [ ] Every unfamiliar term is defined, as a noun phrase, with each term under its own `##` heading in alphabetical order.

**Feature overview**

- [ ] Opens with what the feature is and what it lets the reader do, then a "For example" paragraph.
- [ ] Includes each section only when its Include when condition is true, with no Key terms section and Best practices, if present, before Next steps.
- [ ] Has a Features section with one subsection for each capability, and no numbered steps or `<Steps>` anywhere.
- [ ] Every heading names what its section covers. Use cases, if present, are real scenarios from this PRD, with no padding.
- [ ] Every user story is behind a use case, and every edge case appears in a table, callout, limitation, or best practice.
- [ ] Every counter says what it counts, and every action has a permission.

**How-to guide**

- [ ] Covers one task, with a verb-phrase title, "Before you begin," results after each procedure, Troubleshoot, and Next steps.

**Release notes**

- [ ] Has the **Version:** line and all five sections in order, with each item in the right section.
- [ ] Every item has an explanation line, bullets, "Why it matters," and a Learn more line.
- [ ] Changed, deprecated, and removed items say who's affected and what to do.
