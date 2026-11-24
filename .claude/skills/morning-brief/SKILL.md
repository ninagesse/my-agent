---
name: morning-brief
description: Builds the user's morning brief for today. Reads today's calendar, has the inbox-triager agent sort today's unread email, and returns the 3 emails to act on plus one block of time to handle them. Read-only. Use when the user asks for their morning brief.
---

# Morning brief

Read-only. Never send, reply, delete, label or change anything. Never create or edit calendar events. Only suggest.

## Step 1: Read today's calendar
Read `ABOUT_ME.md` first (time zone, working hours, protected focus time). Then list today's events on the primary Google Calendar, using the user's time zone.

## Step 2: Triage today's unread email
Hand today's unread email to the `inbox-triager` agent. Take its **Do now** list as the 3 emails to act on. Do not re-rank them yourself. If the agent returns fewer than 3, say so.

## Step 3: Pick one focus block
Choose one block of time today to deal with the Do now emails:
- 60 minutes (shorter if the list is short).
- Inside the working hours from `ABOUT_ME.md`.
- Not overlapping any calendar event from Step 1.
- Not inside the protected focus time from `ABOUT_ME.md`.
- Not already in the past. If nothing fits today, say so and suggest the first fitting slot tomorrow.

Suggest the block. Do not create it.

## Output
Plain words, honest and focused:
1. **Today's calendar**: events in time order.
2. **Do now**: the 3 emails, one line each on why and what to do.
3. **Suggested block**: day, time and why it fits.
4. **Left out**: anything important the triager could not fit, if any.
