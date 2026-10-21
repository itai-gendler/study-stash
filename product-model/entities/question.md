---
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AiAskModel.cs
- kind: code
  role: implementation
  target: web/src/screens/Ask.tsx
- kind: code
  role: implementation
  target: ios/StudyStash/Screens/Ask/AskViews.swift
---

# Question

One question to Ask and the answer shown for it. Phone Ask retains recent questions on that device; a saved library chat is a separate conversation.

## Information kept

- **Question** — The question the student asked.
- **Scope** — One lecture, one class or all lecture material.
- **Answer** — The text received so far.
- **Sources** — The lecture or attachment passages cited by the answer, with source moments when known.
- **Engine** — The engine that answered.
- **Problem** — Why the answer stopped or could not be produced.

## States

### Answering

An answer is being requested or streamed.

### Answered

An answer or an explanation that no matching source was found is available.

### Failed

The request ended with a problem.

### Stopped

The desktop student stopped the current answer.
