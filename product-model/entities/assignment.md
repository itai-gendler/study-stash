---
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Canvas/Assignments.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Canvas/CanvasIndex.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.Canvas.cs
---

# Assignment

A mirrored Canvas assignment with the student’s submission and feedback. Its status is read from Canvas rather than submitted in Study Stash.

## Information kept

- **Title** — The assignment name and kind.
- **Due** — The due date or no due date.
- **Status** — Open, missing, submitted, graded, excused or marked done as derived from Canvas.
- **Instructions** — The task description.
- **Rubric** — The marking criteria and any awarded marks.
- **Submission** — The student’s submitted text, links or files.
- **Feedback** — The grader’s comments, grade and score.
- **Link** — Where to open the assignment in Canvas.
