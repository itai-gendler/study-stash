---
appliesTo:
- type: entity
  id: lecture
  effect: reads
  contexts:
  - place: ai-apps
  facts:
  - Title
  - Class
  - Date
  - Duration
  - Topics
  - Filed copy
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/ToolAccess.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/ClaudeTools.cs
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
    fact: Lectures and transcripts
    is: true
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

# AI apps see which lectures there are only while Lectures and transcripts or Study notes is on

A lecture’s title, class, date, length and topics come with whichever lecture material an AI app is allowed to read.
