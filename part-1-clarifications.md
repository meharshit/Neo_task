# Questions before writing the Tracks docs

These are some of my doubts about the Tracks feature and the assumptions I made while writing the docs.

## Questions

| # | Question | Who can answer it | Assumption I took |
|---|---|---|---|
| 1 | The PRD says two different things about turning off Tracks. One section says it hides everything and restores it later. Another says it clears everything. Which is right? | PM | It clears everything, and the docs warn that it can't be undone. |
| 2 | Who can delete a track? It's the only permanent track action, and it's missing from the permissions table. | PM | Any team member. |
| 3 | What do the two counters count? For the column's "X out of Y," what are X and Y? For the pill's "Done out of all available tracks," is that every track in the project, or only the tracks the task is on? | Dev | Column: Done tasks out of all open tasks on the track. Pill: Done tracks out of the tracks the task is on. |
| 4 | What does Stop do? And because a Done task can't be stopped, is Mark Pending, then Stop, the intended way to take it off a track? | PM | Stop moves the task back to Not started on that track. Yes to Mark Pending, then Stop. |
| 5 | Can you share designs or a build? I need to see where the Tracks switch is, where a track's Rename, Move track, and Delete actions are, and how a task gets onto its first track. | Dev | The switch is on the project's Settings tab, the track actions are on the column header, and a task is first started from its Tracks pill. |
| 6 | Can guests turn on Tracks and add, rename, or delete tracks, even though they're from another organization? | PM | Yes, the same as members. Only admins can turn Tracks off. |
| 7 | Do Stop and Select work offline? And when an offline change is dropped because its track was deleted, does the user see anything? | Dev | Both are online only, and the user isn't told. |
| 8 | Can someone change track statuses on a closed task from the pill? | Dev | No. The pill is read-only until the task is reopened. |
| 9 | What's the version number for this release? | PM | The release notes use `[Version]` until you confirm it. |

## Assumptions

I made the following assumptions while writing the docs:

- Tracks is off by default for every project.
- Finishing every track doesn't complete the task automatically.
- Deleting a track and turning off Tracks both ask for confirmation.
- Track names must also be unique when you rename a track, and there's no limit on the number of tracks.
- Moving a task to another project doesn't warn the user that the move clears its tracks.
- "Work tab" in the PRD means My Work, and a task's Friday chat is its conversation with Friday.
