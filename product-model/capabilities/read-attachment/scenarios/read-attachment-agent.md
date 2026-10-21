---
kind: primary
routes:
  ai-apps: AI apps
steps:
- text: The connected AI app requests an attachment’s words.
  kind: actor
  actor: ai-agent
  entities:
  - entity: attachment
    effect: reads
    facts: []
  contexts: &id001
    ai-apps:
      place: ai-apps
- text: The Product returns the attachment information and requested content.
  kind: product
  entities:
  - entity: attachment
    effect: reads
    facts:
    - Name
    - Kind
    - Size
    - Added
    - Text
    - Used in notes
  contexts: *id001
  actor: ai-agent
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AttachmentsModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Attachments.cs
- kind: code
  role: implementation
  target: web/src/screens/attachments.tsx
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Library/ClassView.swift
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/ClaudeTools.cs
---

# Read attached material

## Trigger

The connected AI app requests an attachment’s words.

## Outcome

The original file or available extracted words are presented, including whether reading is still in progress.

## Edge cases

- PDFs and pictures can be opened inline on the library web page; other types download.
- The AI tool pages long extracted text rather than returning the entire file at once.
