---
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AiAccessModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/ClaudeAccess.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/McpClients.cs
---

# AI app connection

A local AI app setup or a granted remote connection shown in AI apps settings.

## Information kept

- **Name** — The app or connection name.
- **Kind** — Local app, remote sign-in or named token.
- **Status** — Added, connected, awaiting an app restart, or needing attention.
- **Last used** — When the app last contacted the library.
