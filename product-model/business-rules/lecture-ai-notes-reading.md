---
appliesTo:
- type: entity
  id: lecture
  effect: reads
  facts:
  - Study notes
  - Your notes
  - Writer
  contexts:
  - place: ai-apps
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/ToolAccess.cs
permits:
- related:
  - verb: studies
    entity: student
  - verb: connects
    entity: ai-agent
  when:
  - entity: ai-settings
    fact: Reading enabled
    is: true
  - entity: ai-settings
    fact: Study notes
    is: true
---

# AI apps read study notes only while Study notes is on

The student’s connected AI app reads a lecture’s notes, including the student’s own words, only while reading for AI apps and Study notes are both switched on.
