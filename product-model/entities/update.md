---
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/Services/AppUpdates.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Updates.cs
---

# Software update

A newer Study Stash release found for this installation.

## Information kept

- **Version** — The offered release version.
- **Progress** — Download or installation progress.
- **Problem** — Why this copy cannot update or an installation failed.

## States

### Available

A newer version is known.

### Waiting

Installation is waiting until recording work is idle.

### Installing

The new version is being installed.

### Installed

The replacement is ready and the app restarts.

### Failed

The existing version remains after an unsuccessful attempt.
