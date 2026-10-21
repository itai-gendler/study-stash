---
kind: primary
routes:
  phone-web-library: Phone web app
steps:
- text: The student asks Ask about all classes or one class.
  kind: actor
  actor: student
  entities:
  - entity: class
    effect: reads
    facts: []
  contexts:
    phone-web-library:
      place: phone-web::library::ask
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
    phone-web-library:
      place: phone-web::library::ask
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
    phone-web-library:
      place: phone-web::library::ask
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
    phone-web-library:
      place: phone-web::library::ask
references:
- kind: code
  role: implementation
  target: web/src/screens/Ask.tsx
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/LibraryReader.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/AiJobs.cs
---

# Ask from the phone web app

## Trigger

The student wants an answer from their own notes and transcripts on the phone.

## Outcome

The answer streams in from the chosen engine, with the lectures and attachments it drew on.

## Edge cases

- An unavailable selected provider can fall back to Ollama when fallback is enabled.
- Once text has been shown, a provider failure does not silently restart the answer with another engine.
- An empty question is not sent.
- A question about an active desktop capture uses the words available so far.

- The phone web Ask form scopes a question to all classes or one selected class.
- Phone Ask retains recent questions locally; these do not become saved library chats.
- If no matching source material is found, Ask says it could not find an answer in the notes.
