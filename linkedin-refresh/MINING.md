# Mining brief

Give each subagent this brief, with the placeholders filled in. One subagent per source.

```
Goal: reconstruct the work history of <full name> (<every known email, username and handle>)
at <employer> from <source>, to feed a LinkedIn profile.

READ-ONLY: search, read and list only. Every message, ticket, repository and document stays
as you found it. Send nothing anywhere.

Privacy: leave out personal and HR content. Old mails and API answers can hold passwords
and tokens; never copy them into the report.

Collect:
1. Identity: every author name and email variant (old domains, typos), account creation
   date, roles and group ownership.
2. Per project and per year: counts, first and last date. Counts rank the work; they are
   not profile material.
3. What the person did, read from titles, descriptions and commit messages. Leave diffs
   and file contents aside.
4. The 20 to 40 most significant items, each with date, link and one line.
5. Role evidence: reviews of others' work, ownership, hiring, tutoring, mentoring,
   incidents handled, thanks received.
6. Recurring tasks and the tech stack.

<source hints from the list below>

Write Markdown to <report path> with sections: Identity, Timeline by year, Projects,
Candidate bullets (each with its evidence), Recurring tasks, Skills evidence, Gaps.
Final reply: a 15-line summary and the file path.
```

## Source hints

- **Git hosting**: merge requests authored in every state, merge requests where the person is the reviewer, issues created or assigned, epics. The events API may have pruned old events; say so in Gaps.
- **Local clones**: find every author identity first. Count each commit once: copies of a clone and split repositories share history. `git-svn-id` lines reveal history imported from SVN.
- **Ticket tools**: issues assigned, authored and updated. Deleted projects vanish from the API but survive in mail notifications.
- **Mailbox**: search counts are capped, so probe by date range. Titles appear in signatures. The earliest mail and the account activation mails give the start date. Notifications from retired tools (Taiga, SVN, Jenkins) rebuild the years before the current tools.
- **Chat**: search returns few hits per query, so query year by year. Read the incident channels and the threads where the person answers others. Search for thanks addressed to them.
