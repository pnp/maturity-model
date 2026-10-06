---
name: update-practitioners-calls-archive
description: "Use when asked to add new Microsoft 365 Maturity Model Practitioners Calls sessions to the archive, finding and verifying published recordings."
argument-hint: "Optionally provide a date range, session topic, or recording URL"
user-invocable: true
disable-model-invocation: false
---

# Update Practitioners Calls Archive

Find published Microsoft 365 Maturity Model Practitioners Calls recordings and add verified, missing sessions to [the archive](../../../docs/overview/practitioners-calls-archive.md).

## Scope

- Update only the archive's session entries, matching table of contents, and `ms.date`.
- By default, search for sessions after the newest archived session through today's date. If the user supplies a date range, topic, or recording URL, use that scope instead, including older missing sessions when requested.
- Do not assume a call occurred every month. Do not add scheduled events, announcements without a published recording, or unrelated Microsoft 365 community calls.
- Preserve existing summaries, credits, includes, images, footer, and unrelated worktree changes. Do not edit generated site output.
- Do not commit or push unless explicitly requested.

## Step 1: Establish the Baseline

1. Read the archive in full and check the worktree for existing changes.
2. Identify the newest session by its session date, not by `ms.date`.
3. Inventory the existing session headings, dates, recording URLs, table-of-contents anchors, speaker links, and tag conventions.
4. Use recording IDs as the primary duplicate check. Normalize YouTube watch, short, live, and share URLs to their video IDs for comparison.
5. Also compare session dates and topics to catch alternate uploads of an already archived call. Different recordings in the same month are not automatically duplicates. If two sources may describe the same call and the distinction cannot be verified, ask before adding it.

## Step 2: Discover Published Sessions

Use public web search, web fetch, or browser tools available in the session. Do not send repository contents or private information to external services.

1. Start with the publishers or playlists linked from existing archive recordings and the public practitioners links in [the practitioners include](../../../docs/includes/mm4m365-practitioners.md).
2. Search for phrases such as `Maturity Model for Microsoft 365 Practitioners Call`, `MM4M365 practitioners`, and the relevant month or year. Search wording may vary; confirm the event identity rather than relying on its title alone.
3. Prefer the original recording publisher and official Microsoft 365 & Power Platform community or PnP recap pages. Search results are discovery aids, not sufficient evidence by themselves.
4. Open each candidate's recording and available recap. Confirm it is a published practitioners call within scope.
5. Verify the date of the call from the description, recap, or recording. An upload date is not necessarily the session date. Never substitute one silently.
6. Verify the topic, presenters, recording URL, and any profile links or credentials. Reuse an existing speaker link only when it clearly identifies the same person; otherwise use a verified public profile or plain text.
7. Keep a working evidence record for each candidate: session date, topic, recording ID and URL, presenters, source URLs, and available summary evidence. Keep this in session context rather than adding a notes file to the repository.

If discovery tools fail or a page is inaccessible, try another public source or tool. Report remaining limitations explicitly; an incomplete search is not proof that no new sessions exist.

## Step 3: Obtain Evidence and Write the Summary

Read an accessible transcript, captions, official session recap, or sufficiently detailed recording description before writing a summary.

- Never invent presentation details from the title, thumbnail, or a related competency document.
- If the available evidence is insufficient, ask the user for a transcript, recap, or other session material. Leave that candidate out of the archive until enough evidence is available; report it as pending.
- Write an original summary, not a reproduced transcript or recap. Match the archive's substantive, multi-paragraph narrative style when the evidence supports it, but do not pad a short source with speculation.
- Cover the session's central argument, important maturity-model connections, practical examples, and useful discussion or takeaways supported by the source.
- Distinguish the speaker's proposals or opinions from established model guidance. Attribute time-sensitive claims to the session rather than presenting them as newly verified facts.
- Prefer paraphrases. Use only brief, verified quotations when they add value; do not turn uncertain captions into confident quotations.
- Include only verified presenters and credentials. Do not treat every Q&A participant as a presenter.
- Select relevant tags using the archive's existing competency names and topic-tag conventions. Do not invent a new competency from the session title.

## Step 4: Update the Article

For each fully verified missing session:

1. Insert its section into `## Practitioners Calls Archive` in reverse session-date order. Preserve the relative order of existing entries. For calls in the same month, use verified day dates for ordering; if those are unavailable, preserve existing order and place the new entry next to that month's entries without claiming a day.
2. Add one corresponding entry under `## Table of Contents` in the same order.
3. Use a concise, distinctive heading based on the verified topic. If a topic repeats, append the month and year to the new heading to avoid duplicate anchors. Do not rename old headings merely to accommodate a new entry.
4. Compute the table-of-contents fragment from the actual heading using the site's heading-ID behavior, including punctuation and repeated hyphens. Use nearby entries as examples; verify against rendered output when available. Do not blindly replace every space and punctuation mark with a single hyphen.
5. Follow this entry shape:

```markdown
### <Verified session topic>

<Month YYYY> | Recording: <a href="<verified recording URL>" target="_blank">YouTube</a>

**Speaker(s):** <a href="<verified profile URL>" target="_blank"><Verified speaker name and credentials></a>

**Summary:** <Original, source-grounded opening paragraph.>

<Additional source-grounded paragraphs as warranted.>

`<Existing tag>`, `<Existing tag>` | [→ Back to top](#table-of-contents)

---
```

Use `<br>` between multiple presenters, as in existing entries. Use plain text for a presenter without a verified profile. If a verified recording is hosted elsewhere, use its actual host as the link label rather than calling it YouTube.

Update `ms.date` to today's date in `MM/DD/YYYY` format only when the article changes. Do not change the other front matter.

If no verified missing sessions are found, make no file changes, including no date-only update.

## Step 5: Validate

- Every added session has one section and one table-of-contents entry, with matching topic and month/year.
- The table-of-contents order matches the session-section order, and both are newest first.
- Every new table-of-contents anchor resolves to its intended heading; headings do not create duplicate IDs.
- No added recording ID or session duplicates an existing entry or another addition.
- Recording URLs, speaker links, and any new material links resolve to the intended resources. Report inaccessible links rather than claiming they passed validation.
- Each new entry has a verified date, recording, presenter list, evidence-based summary, tags, back-to-top link, and separator.
- Existing entries and publishing elements remain unchanged apart from the intended insertions and date update.
- Review the final diff and run `git diff --check`. Use any existing relevant documentation validation if available; do not install new tooling just for this update.
- Invoke the skill again conceptually against the resulting archive: all added recording IDs must now be recognized as existing, so a repeat with the same discovered sessions would make no changes.

## Step 6: Report

Summarize:

- Sessions added, with their dates and topics.
- The updated article path and validation results.
- Public evidence links used for each addition.
- Candidates left pending, unavailable transcripts, unresolved dates, and any search limitations.

If nothing was added, say whether no missing sessions were found in the searched scope or whether verification was blocked. Do not claim the archive is complete beyond the scope and sources actually checked.
