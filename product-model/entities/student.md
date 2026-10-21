---
acts: external
kind: person
relations:
- entity: ai-agent
  verb: connects
  cardinality: one-to-many
- entity: lecture
  verb: studies
  cardinality: many-to-many
- entity: class
  verb: studies
  cardinality: many-to-many
- entity: attachment
  verb: uses
  cardinality: many-to-many
- entity: assignment
  verb: studies
  cardinality: many-to-many
- entity: course-material
  verb: studies
  cardinality: many-to-many
- entity: announcement
  verb: studies
  cardinality: many-to-many
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/AppHost.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Devices.cs
---

# Student

The person keeping a personal lecture library, recording classes and studying from their own material.

## Information kept

- **Display name** — The name attached to recordings.
- **Library access** — Whether the current client has an established library connection.
- **AI connection** — Whether the person has connected an AI app to this library.
