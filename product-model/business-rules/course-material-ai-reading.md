---
appliesTo:
- type: entity
  id: course-material
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

# AI apps read course material only while Canvas assignments and files is on

The student’s connected AI app reads a class’s modules, files and pages only while reading for AI apps and Canvas assignments and files are both switched on.
