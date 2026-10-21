---
relations:
- entity: lecture
  verb: contains
  cardinality: one-to-many
- entity: attachment
  verb: contains
  cardinality: one-to-many
- entity: assignment
  verb: contains
  cardinality: one-to-many
- entity: course-material
  verb: contains
  cardinality: one-to-many
- entity: announcement
  verb: contains
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Config.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/ClassRename.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/LibraryReader.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/CanvasClassModel.cs
---

# Class

A named folder for lectures and associated material; folders can also belong to a club, work, or a group named by the student.

## Information kept

- **Name** — The class or folder name.
- **Description** — What it covers, used when sorting lectures.
- **Other names** — Aliases including previous names and course codes.
- **Group** — The group the folder belongs to.
- **Canvas course** — The course linked to this class, if any.
- **Modules** — The ordered Canvas modules and their items.
- **Lecture count** — How many filed lectures belong here.
