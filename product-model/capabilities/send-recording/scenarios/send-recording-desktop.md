---
kind: primary
routes:
  desktop: Desktop app
steps:
- text: A transcribed desktop recording is ready to send.
  kind: condition
  unattended: true
  entities:
  - entity: recording
    effect: reads
    facts: []
  contexts: &id001
    desktop:
      place: desktop::recording
- text: The Product sends the recording transcript and notes and retains its audio locally.
  kind: product
  entities:
  - entity: recording
    effect: changes
    facts:
    - Delivery
    from: Sending
    to: Writing
  contexts: *id001
- text: The Product queues the lecture with the supplied material.
  kind: product
  entities:
  - entity: lecture
    effect: creates
    facts:
    - Title
    - Class
    - Date
    - Recorder
    - Duration
    - Transcript
    - Your notes
    - Study notes
    - Writer
    - Topics
    - Filing choice
    - Problem
    - Filed copy
    to: Queued
  contexts: *id001
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Recording/Recorder.cs
- kind: code
  role: implementation
  target: ios/StudyStash/Recording/Recording.swift
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.PhoneLectures.cs
---

# Send from the computer

## Trigger

A transcribed desktop recording is ready to send.

## Outcome

The library accepts the lecture once and the desktop follows its progress.
