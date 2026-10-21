---
entities:
- entity: ai-connection
  shows:
  - Name
  - Kind
  - Status
  - Last used
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/ClaudeAccess.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/ClaudeWeb.cs
---

# Allow an AI app

The page an AI app on the web opens to connect: the library password, then Allow.
