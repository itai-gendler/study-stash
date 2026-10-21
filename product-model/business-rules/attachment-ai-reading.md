---
appliesTo:
- type: entity
  id: attachment
  effect: reads
  contexts:
  - place: ai-apps
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/ToolAccess.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/ClaudeTools.cs
permits:
- related:
  - verb: uses
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

# AI apps read attachments only while Study notes is on

The student’s connected AI app lists and reads attached files only while reading for AI apps and Study notes are both switched on.
