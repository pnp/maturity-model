---
name: create-blog-post
description: "Use when asked to create a blog post for the Maturity Model site, including a Practitioners Call archive post from an issue created with the Practitioners Call post form."
argument-hint: "The issue number, or the post type plus its inputs"
user-invocable: true
disable-model-invocation: false
---

# Create a Blog Post

Create one post under `docs/blog/` and list it in the blog index.

## Post types

Every post has a `type` in its front matter. The type decides the template and the inputs.

| Type | Use for | Inputs | Template |
|---|---|---|---|
| `archive` | One recorded Practitioners Call | Practitioners Call post issue form | [Archive post](#archive-post) |

Add a new type by adding a row here and a template section below. Do not invent a type that is not in the table.

## Rules for every post

- All facts come from the issue (or the user). Never invent people, credentials, quotes, dates or links. Leave a section out rather than guess.
- File name: `docs/blog/YYYY-MM-DD-<slug>.md`, using the event date for `archive` and the publish date otherwise.
- Add the post at the top of its type's list in `docs/blog/index.md` (newest first) and to `docs/blog/toc.yml` (newest first).
- Run `git diff --check`, check that every relative link resolves, and open a PR that says `Fixes #<issue>` and lists anything left out for lack of evidence.

## Archive post

### Inputs

Session date, topic, speakers, speaker plugs, recording URL, slides link, transcript, links mentioned.

- Do not fetch the YouTube transcript or watch the video. The transcript is pasted into the issue. If it is missing, stop and ask for it in the issue.
- The session date is the date of the call, not the upload date.
- Speaker plugs come only from the issue, never from the transcript.
- Check the recording ID against existing archive posts and the legacy archive page; do not create a duplicate.

### Chapters

Build chapters only from timestamps in the transcript (YouTube's copied transcript has `m:ss` lines; `.vtt` has cue times). Aim for 5–10 chapters at real topic shifts. Each links to `https://www.youtube.com/watch?v=<ID>&t=<seconds>s`. Without timestamps, omit Chapters and say so in the PR.

### Summary

Summarise the main presentation, not the community news at the start or the closing housekeeping. Follow Step 3 of the `update-practitioners-calls-archive` skill: original, source-grounded, opinions attributed to the speaker, no padding. Tags use the existing competency names.

### Template

The post uses the blog styles in `docs/templates/material/styles/main.css` (classes starting with `mm-`). Keep the structure exactly; only the content changes. Leave out a whole section (heading and block) when the issue gives nothing for it.

```markdown
---
title: "<Topic>"
type: archive
date: <YYYY-MM-DD of the session>
ms.date: <MM/DD/YYYY today>
author: <GitHub handle of the issue author>
ms.topic: overview
ms.service: microsoft-365
ms.collection: M365Community
description: "Practitioners Call, <Month YYYY>: <one sentence on what the session covered>."
_disableAffix: true
---

<div class="mm-home mm-post">

<div class="mm-post-head">
<p class="mm-eyebrow">Practitioners Call · <D Month YYYY></p>
<h1><Topic></h1>
<p class="mm-post-who"><img src="../media/speakers/<first-last>.jpg" alt="" width="48" height="48" /><span><strong><Name></strong>, <credentials><br /><Role, Company></span></p>
<p class="mm-pills"><a class="mm-pill" href="../competencies/<file>.md"><Competency></a></p>
</div>

> [!Video https://www.youtube-nocookie.com/embed/<ID>]

## Chapters

<div class="mm-chapters">

- [0:00](https://www.youtube.com/watch?v=<ID>&t=0s) <Chapter title>

</div>

## Summary

<Paragraphs.>

## Key takeaways

<div class="mm-takeaways">

- **<Point in bold.>** <One sentence.>

</div>

## Presentation

<div class="mm-deck">
<object class="mm-deck-embed" data="files/<YYYY-MM-DD-slug>.pdf#navpanes=0&amp;view=FitH" type="application/pdf" aria-label="Slides: <Topic>"></object>
<a class="mm-deck-card" href="files/<YYYY-MM-DD-slug>.pdf" download><span class="mm-deck-icon" aria-hidden="true">PDF</span><span><strong>Download the slides</strong><span>PDF, <size> MB</span></span></a>
</div>

## About the speaker

<div class="mm-speaker">
<img class="mm-photo" src="../media/speakers/<first-last>.jpg" alt="<Name>" width="96" height="96" />
<div>
<p class="mm-speaker-name"><Name, credentials></p>
<p><One or two sentences from the speaker's public profile.></p>
<p class="mm-speaker-links"><a href="<URL>">LinkedIn</a><a href="<URL>">Blog</a></p>
<p class="mm-speaker-plugs"><Plug from the issue> – <a href="<URL>"><title></a></p>
</div>
</div>

<p class="mm-post-back"><a href="index.md">← All posts</a></p>

</div>
```

- Keep a blank line after every opening `<div>` and before every closing `</div>` that wraps Markdown, or the Markdown inside is not rendered.
- Speaker photo: save the speaker's Sessionize photo as `docs/media/speakers/<first-last>.jpg`, 240 × 240 px. Without a photo, use `<span class="mm-photo mm-avatar mm-bg1" aria-hidden="true"><Initials></span>` (and `mm-avatar mm-bg1` without `mm-photo` in the header).
- Slides: download the PDF linked in the issue's "Presentation (PDF)" field and commit it as `docs/blog/files/<YYYY-MM-DD-slug>.pdf` (same name as the post). Never commit a .pptx. Remove any slide that lists attendee names (the "Thank you, <month> attendees!" slide) before committing; attendees did not agree to be published on the site. If the PDF is over 10 MB, stop and ask in the issue for a smaller export. Without a PDF, leave the whole Presentation section out.
- Several speakers: one `mm-post-who` line and one `mm-speaker` block each. Use "About the speakers".

### Card on the blog index

Add a card at the top of `<div class="mm-posts">` in `docs/blog/index.md`. The first card has `mm-post-featured`; remove that class from the card that had it.

```html
<a class="mm-post-card mm-post-featured" href="<YYYY-MM-DD-slug>.md">
<span class="mm-post-art"><img src="https://i.ytimg.com/vi/<ID>/hqdefault.jpg" alt="" loading="lazy" /><span class="mm-play" aria-hidden="true"></span></span>
<span class="mm-post-body">
<span class="mm-post-date"><D Month YYYY> · Practitioners Call</span>
<strong><Topic></strong>
<span class="mm-post-who"><img src="../media/speakers/<first-last>.jpg" alt="" width="40" height="40" /><Name, credentials></span>
<span class="mm-post-excerpt"><One or two sentences.></span>
<span class="mm-pills"><span class="mm-pill"><Competency></span></span>
</span>
</a>
```

### Competency links

| Competency (form) | File in `docs/competencies/` |
|---|---|
| Business Process | `microsoft365-maturity-model--business-process.md` |
| Cognitive Business (AI) | `microsoft365-maturity-model--cognitive-business.md` |
| Collaboration | `microsoft365-maturity-model--collaboration.md` |
| Communication | `microsoft365-maturity-model--communication.md` |
| Governance, Risk & Compliance | `microsoft365-maturity-model--governance-and-compliance.md` |
| Management of Content | `microsoft365-maturity-model--management-of-content.md` |
| People & Communities | `microsoft365-maturity-model--people-and-communities-competency.md` |
| Security | `microsoft365-maturity-model-security.md` |
| Staff & Training | `microsoft365-maturity-model--staff-and-training.md` |

For a competency not in the table, find its file in `docs/competencies/toc.yml`.
