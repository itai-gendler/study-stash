---
entities:
- entity: ai-settings
  shows:
  - Reading enabled
  - Lectures and transcripts
  - Study notes
  - Canvas assignments and files
  - Web access
  collects:
  - Reading enabled
  - Lectures and transcripts
  - Study notes
  - Canvas assignments and files
  - Web access
- entity: ai-connection
  shows:
  - Name
  - Kind
  - Status
  - Last used
references:
- kind: code
  role: implementation
  target: engine/src/StudyStash.App/ViewModels/AiAccessModel.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/Ai/ToolAccess.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/ClaudeAccess.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Core/McpClients.cs
- kind: code
  role: implementation
  target: engine/src/StudyStash.Library/LibraryWeb.App.cs
---

# AI apps settings

Settings’ AI apps page on the library’s computer: whether AI apps may read the library and which material, the apps on this computer with Connect or Disconnect, and connections made from the web.
