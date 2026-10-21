---
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/Rewrites.cs
---

# Rewrite

An attempt to prepare new notes while leaving the current write-up in place.

## Information kept

- **Engine** — The AI chosen for this attempt.
- **Progress** — The work completed and remaining.
- **Started** — When the attempt began.
- **Problem** — Why a rewrite did not complete.

## States

### Working

The AI is preparing a replacement.

### Ready

A proposed replacement is available.

### Failed

The attempt produced no usable replacement or was interrupted by a library restart.

### Cancelled

The student stopped the attempt.
