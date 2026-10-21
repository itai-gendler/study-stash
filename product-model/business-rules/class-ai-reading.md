---
appliesTo:
- type: entity
  id: class
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
---

# AI apps list classes only while reading for AI apps is on

The class list, with how many lectures each class has, needs only reading for AI apps to be on.
