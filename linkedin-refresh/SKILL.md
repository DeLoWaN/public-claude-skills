---
name: linkedin-refresh
description: Rebuild a LinkedIn profile from the evidence in the user's work tools, then update it in the browser with the user's approval.
disable-model-invocation: true
---

# LinkedIn refresh

Rebuild the user's LinkedIn profile (headline, About, positions, skills) from **evidence**: facts found in their work tools, each one tied to a source. You find the facts. The user makes every decision. Talk to the user in their own language.

Two rules hold in every step:

- **Read-only** on every source. Search, read and list only. Every message, ticket, repository and document stays as you found it.
- **Evidence** before words. Every claim in the draft traces to a source or to an answer from the user. A number appears only after the user confirms it.

## 1. Frame the job

Run a grilling session (use the `/grilling` skill when it is installed). Ask in rounds, number each question, give your recommended answer, and wait for the answers. Settle at least:

1. The goal: profile update, job search, or internal move.
2. The deliverable: LinkedIn only, or a CV file too.
3. The languages: one profile, or a second-language profile as well.
4. The scope: current employer only, or the whole career. Ask whether texts for older jobs already exist.
5. The clients: named, anonymised, or left out.
6. The work that leaves no trace: on-call, hiring, mentoring, informal lead role, training given.
7. The sources to mine (step 2 lists how to find them).

Done when the user has answered every question in their own words.

## 2. Mine the evidence

List what is connected: MCP servers, CLIs such as `glab` or `gh`, local git clones. Show the list to the user, and let them pick.

Dispatch one background subagent per chosen source, all in parallel, with the brief in [MINING.md](MINING.md). While they run, ask the step 1 questions that do not depend on their results.

| Source | What it reveals |
|---|---|
| Git hosting (GitLab, GitHub) | Merge requests, issues, epics, reviews given, group ownership |
| Local git clones | Commit history over the years, including history imported from SVN |
| Ticket tools (Redmine, Jira) | Support and project tickets, who asked for what |
| Mailbox | Start date, titles in signatures, notifications from retired tools, hiring and tutoring |
| Chat (Slack, Teams) | Incidents, decisions, help given, thanks received |

Done when every chosen source has a report file and you have read every report in full.

## 3. Triage

Merge the reports into one list of 25 to 30 achievements. Give each one a title, dates, one line of text, and the letters of its sources. Merge duplicates across sources. Rank by impact and by the number of independent sources, in three tiers: pillars, strong, secondary.

Write the list to a Markdown file and ask the user to strike items. Drop every item that the user strikes or does not remember: a claim they cannot defend in an interview stays off the profile.

Done when the user has returned the list.

## 4. Draft

Write one Markdown file with one section per LinkedIn block: headline, About, one section per position, and skills (5 top skills, then the rest). When a second language is in scope, write it in a second file after the user validates the first one.

- **Limits**: headline 220 characters, About 2,600, each position description 2,000. Count with a script after every edit, and report the counts.
- **About** covers the whole career. LinkedIn shows about three lines before "see more", so lead with the current role.
- **Style**: ask for first person, verb-led or noun-led bullets, and apply the choice everywhere.
- **Specifics**: name the tools and the results. For AI work, name what the user built.
- **Titles**: the user chooses between the official title and a functional one.

Show the draft with its counts, and revise until the user validates each block.

Done when the user has validated every block.

## 5. Update LinkedIn

Only when the user asks. Read [LINKEDIN-EDITING.md](LINKEDIN-EDITING.md) before the first click. Confirm with the user the exact list of changes and the network notification setting, then edit one section at a time.

Done when the profile, viewed in each language, shows every validated block, and each character counter matches the count from step 4.

## 6. Review the rest

Check the other sections and propose fixes, most important first: formatting and translation of older positions, titles that contradict the About text, stale certifications, skills attached to the wrong entries, recommendations. Apply the fixes the user picks, with the step 5 rules.

Done when the user has decided on every proposed fix.
