---
appliesTo:
- type: entity
  id: assignment
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
  - verb: studies
    entity: student
  - verb: connects
    entity: ai-agent
  when:
  - entity: ai-settings
    fact: Reading enabled
    is: true
  - entity: ai-settings
    fact: Canvas assignments and files
    is: true
---

# AI apps read assignments only while Canvas assignments and files is on

The student’s connected AI app reads what is due and each assignment only while reading for AI apps and Canvas assignments and files are both switched on.
