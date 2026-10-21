---
appliesTo:
- type: entity
  id: lecture
  effect: reads
  facts:
  - Transcript
  - Search passages
  contexts:
  - place: ai-apps
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
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/ToolAccess.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/ClaudeTools.cs
---

# AI apps read transcripts and search passages only while Lectures and transcripts is on

Listing lectures, searching them and reading a transcript need reading for AI apps and Lectures and transcripts to be switched on.
