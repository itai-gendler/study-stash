---
type: web
actors:
- student
references:
- kind: code
  role: implementation
  target: web/src/App.tsx
- kind: code
  role: implementation
  target: web/src/router.ts
- kind: code
  role: implementation
  target: web/src/api/client.ts
entryPoints:
- web: /app/
---

# Phone web app

The installable phone web app reads a paired library, asks questions and sends attachments or voice memos.
