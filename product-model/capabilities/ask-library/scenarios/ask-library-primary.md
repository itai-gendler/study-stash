---
kind: primary
routes:
  desktop: Desktop app
  ios-library: iPhone and iPad app
steps:
- text: The student asks Ask about one lecture, one class or all of them.
  kind: actor
  actor: student
  entities:
  - entity: class
    effect: reads
    facts: []
  - entity: lecture
    effect: reads
    facts: []
  contexts:
    desktop:
      place: desktop::ask
    ios-library:
      place: ios::library::ask
- text: The Product keeps the question and its selected scope.
  kind: product
  actor: student
  entities:
  - entity: question
    effect: creates
    facts:
    - Question
    - Scope
    to: Answering
  contexts:
    desktop:
      place: desktop::ask
    ios-library:
      place: ios::library::ask
- text: The Product reads the relevant lecture and attachment material and streams an answer.
  kind: product
  entities:
  - entity: lecture
    effect: reads
    facts:
    - Title
    - Class
    - Transcript
    - Study notes
  - entity: attachment
    effect: reads
    facts:
    - Text
  contexts:
    desktop:
      place: desktop::ask
    ios-library:
      place: ios::library::ask
  actor: student
- text: The Product presents the question’s answer, engine and cited sources.
  kind: product
  actor: student
  entities:
  - entity: question
    effect: changes
    facts:
    - Answer
    - Engine
    - Sources
    from: Answering
    to: Answered
  contexts:
    desktop:
      place: desktop::ask
    ios-library:
      place: ios::library::ask
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

# Ask your library

## Trigger

The student wants an answer from their own notes and transcripts.

## Outcome

The answer streams in from the chosen engine, with the lectures and attachments it drew on.

## Edge cases

- An unavailable selected provider can fall back to Ollama when fallback is enabled.
- Once text has been shown, a provider failure does not silently restart the answer with another engine.
- An empty question is not sent.
- A question about an active desktop capture uses the words available so far.

- A lecture-scoped question uses that lecture’s material; a class-scoped question uses the selected class.
- Phone Ask retains recent questions locally; these do not become saved library chats.
- If no matching source material is found, Ask says it could not find an answer in the notes.
