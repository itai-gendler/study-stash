---
kind: edge
routes:
  phone-web-library: Phone web app
  ios-library: iPhone and iPad app
steps:
- text: A saved request was still waiting when the phone app closed.
  kind: condition
  unattended: true
  entities:
  - entity: question
    effect: reads
    facts: []
  contexts:
    phone-web-library: &id001
      place: phone-web::library::ask
    ios-library: &id002
      place: ios::library::ask
- text: The Product marks the question as interrupted and keeps any answer received.
  kind: product
  entities:
  - entity: question
    effect: changes
    facts:
    - Problem
    from: Answering
    to: Failed
  contexts:
    phone-web-library: *id001
    ios-library: *id002
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AiAskModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/LibraryReader.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/AiJobs.cs
- kind: code
  role: implementation
  target: web/src/screens/Ask.tsx
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Ask/AskViews.swift
---

# Keep an interrupted phone question

## Trigger

The phone Ask screen reopens with a request left unfinished.

## Outcome

The previous question and any partial answer stay readable, with an interruption explanation.
