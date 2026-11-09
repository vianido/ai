---
name: vianido-updates
description: Draft, publish, schedule and manage the updates (posts on the profile feed) of an organization the user manages on Vianido with the update and media tools. Use when the user wants to post news, a milestone, a report, an event or any other update, or to edit, feature or archive one.
---

# Managing updates

A new update is a draft; nothing reaches the profile until it is published. For the words, follow `vianido-writing`. If you can't find the update tools, search the connection's tools first; some clients load them on demand. Still missing: ask the user to reconnect and approve edit access; if they still don't appear, the server predates them and the user posts updates on the Vianido website.

## Start

`list_my_organizations` if you don't know which organization, then `list_organization_updates` and tell the user what is there: recent published updates, drafts, scheduled ones and the featured one. A draft may be someone else's unfinished work; ask before changing or publishing it.

## Choose the type

Most posts are a general update: anything the organization would put on Facebook or Instagram, a few lines with photos or a video. Use it when nothing else fits. Pick another type only when the post is one: a milestone (a number reached, with what it counts), a report (a document to attach), an event (something to attend), a call to action (a request with a link), a partnership (a new partner, or a grant received or given), a leadership change, the organization's own press release, or a news mention (coverage elsewhere, linked).

Updates are not only good news. A paused program, a funding gap, a closed site or a hard month belongs on the record too; help say it plainly rather than steer away from it.

Imported social posts can't be edited. They can be archived, featured or moved to draft.

## Media

Reuse what `list_organization_media` holds before uploading, and upload only files the user provides or confirms the organization owns. Uploading needs a shell or HTTP access, as in `vianido-profile`. Image fields take images, the gallery takes images and videos, a report attachment takes a document. A video is `processing` after upload: a draft or a schedule can hold it, but before publishing now, check it until it is `ready`. If it fails, ask for a re-encoded or different file; uploading the same bytes returns the same failed media.

## Every write

1. Show the update as it will read, with its type and media.
2. Dry-run with `validate_only: true`.
3. Write, then re-read with `get_organization_update` and report.

A change to `content` replaces it whole, nothing is merged: read the update first and send every field you mean to keep. Leave `content` out of a change that only moves state or featuring.

If a create's response is lost, list updates before retrying; a retry can post it twice. Search can miss a recent write, so confirm with the list.

## Publish, schedule, archive

Show the content, name the organization and say what will happen: live now, live at the scheduled time with its time zone, or off the profile now. Act only once the user explicitly approves that action as shown; a request made before they saw it is not enough. Don't rely on the client's approval prompt to catch a mistake; a client that always allows a write tool allows everything that tool can do.

A scheduled update goes live within about five minutes of its time once its media is ready; if that media failed or was removed by then, it returns to draft. Say so when scheduling with a video.

To check publishing a draft, dry-run the change that publishes it. A published edit is live at once. Prefer archiving to taking something down for good; it can be put back.

## Featured

One featured update at a time, shown first on the profile. Featuring one takes the slot from the current one, so name it before you switch. Archiving the featured update leaves the slot empty.

## Keep posting

A profile that posts regularly shows strangers the organization is active. After a first post, and if you can schedule reminders or recurring tasks, offer to remind the user to post. Set it only if they agree.
