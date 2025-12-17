---
doc-id: {GENERATE_UUID}
title: {MEETING_TYPE} - {TOPIC} - {DATE}
description: {MEETING_DESCRIPTION}
aurora-mode: collab
tags: [meeting, {MEETING_TYPE}, {TAGS}]
created: {DATE}
updated: {DATE}
author: {AUTHOR}
meeting:
  type: {MEETING_TYPE}
  date: {DATE}
  time: {TIME}
  duration-minutes: {DURATION}
  location: {LOCATION}
attendees:
  present: [{PRESENT}]
  absent: [{ABSENT}]
series: {SERIES_NAME}
previous: "{PREVIOUS_MEETING_LINK}"
---

# {MEETING_TYPE} - {TOPIC}

**Date**: {DATE} at {TIME}
**Attendees**: {PRESENT}
**Absent**: {ABSENT}
**Duration**: {DURATION} minutes

---

## Agenda

1. {AGENDA_ITEM_1}
2. {AGENDA_ITEM_2}
3. {AGENDA_ITEM_3}

---

## Notes

### {AGENDA_ITEM_1}

Notes here.

### {AGENDA_ITEM_2}

Notes here.

### {AGENDA_ITEM_3}

Notes here.

---

## Decisions

1. **Decision**: {DECISION_1}
   - *Rationale*: {RATIONALE}
   - *Owner*: {OWNER}

---

## Action Items

| # | Action | Owner | Due | Status |
|---|--------|-------|-----|--------|
| 1 | {ACTION_1} | {OWNER} | {DUE} | Open |
| 2 | {ACTION_2} | {OWNER} | {DUE} | Open |

---

## Related

- [[{PROJECT_LINK}|Project]][^1]
- [[{PREVIOUS_MEETING}|Previous Meeting]][^2]

[^1]: {"rel-type": "supports", "doc-id": "{PROJECT_DOC_ID}", "rel-desc": "Meeting supports this project"}
[^2]: {"rel-type": "follows", "doc-id": "{PREVIOUS_DOC_ID}", "rel-desc": "Continuation of previous meeting"}

---

*Parent: [[Jam-Sync/TOC|Jam & Sync]]*
