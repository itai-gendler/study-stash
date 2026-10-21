---
scope: Core lecture recording, delivery, filing and study workflows across the desktop, library web, phone web, native app
  and connected AI tools.
method: Static inspection of tracked source and repository documentation at e6c2d174ed49dc5f32ca4b15f57f5ef4697558a5.
covered:
- description: Recording, transcription, delivery and uploaded-audio processing.
  paths:
  - engine/src/StudyStash.Core/Recording/
  - ios/StudyStash/Recording/
- description: Library filing, edits, attachments, class naming and reader operations.
  paths:
  - engine/src/StudyStash.Core/Pipeline.cs
  - engine/src/StudyStash.Core/Store.cs
  - engine/src/StudyStash.Core/Store.Edits.cs
  - engine/src/StudyStash.Core/Store.Attachments.cs
  - engine/src/StudyStash.Core/Summarize.cs
  - engine/src/StudyStash.Core/Classify.cs
  - engine/src/StudyStash.Core/LibraryReader.cs
  - engine/src/StudyStash.Core/Attachments.cs
  - engine/src/StudyStash.Core/ClassRename.cs
- description: Desktop library, settings, personal notes and setup views.
  paths:
  - engine/src/StudyStash.App/Shell.Library.cs
  - engine/src/StudyStash.App/Shell.Recording.cs
  - engine/src/StudyStash.App/ViewModels/
  - engine/src/StudyStash.App/Services/
- description: Library browser and connected-phone endpoints and device invitations.
  paths:
  - engine/src/StudyStash.Library/LibraryWeb.cs
  - engine/src/StudyStash.Library/LibraryWeb.App.cs
  - engine/src/StudyStash.Library/LibraryWeb.Phone.cs
  - engine/src/StudyStash.Library/LibraryWeb.PhoneLectures.cs
  - engine/src/StudyStash.Library/LibraryWeb.Devices.cs
  - engine/src/StudyStash.Library/Devices.cs
  - engine/src/StudyStash.Library/VoiceMemos.cs
- description: Phone web library, study, questions and uploads.
  paths:
  - web/src/screens/
  - web/src/api/
  - web/src/data/
- description: Native library, questions, practice and handwritten notebooks.
  paths:
  - ios/StudyStash/Screens/
  - ios/StudyStash/Notebooks/
  - ios/StudyStash/App/
- description: Calendar feeds, Canvas mirror and Granola transfer.
  paths:
  - engine/src/StudyStash.Core/Calendar/
  - engine/src/StudyStash.Core/Canvas/
  - engine/src/StudyStash.Core/GranolaTransfer.cs
- description: AI reading tools, proposed rewrites, chat persistence and rich-note processing.
  paths:
  - engine/src/StudyStash.Core/ClaudeTools.cs
  - engine/src/StudyStash.Core/Ai/ToolAccess.cs
  - engine/src/StudyStash.Core/Ai/Rewrites.cs
  - engine/src/StudyStash.Core/Ai/DiagramJobs.cs
  - engine/src/StudyStash.Core/Ai/Chats.cs
  - engine/src/StudyStash.Core/Ai/AiJobs.cs
- description: Library role copying and self-update behavior.
  paths:
  - engine/src/StudyStash.Core/LibraryMove.cs
  - engine/src/StudyStash.Core/Updates.cs
  - engine/src/StudyStash.Library/Cli.cs
exclusions:
- description: Tests and test fixtures are implementation support, not a separate product surface.
  paths:
  - engine/tests/
  - ios/StudyStashTests/
- description: Build, packaging and developer scripts are not student workflows.
  paths:
  - macos/build-app.sh
  - windows/build.ps1
  - .github/workflows/
  - .github/scripts/
  - ios/release.sh
unmapped:
- description: The AI’s Inbox sorting, change history with undo, class terminal and Settings helper chat.
  paths:
  - engine/src/StudyStash.Core/Ai/Inbox.cs
  - engine/src/StudyStash.Core/Ai/History.cs
  - engine/src/StudyStash.Core/Ai/Terminal.cs
  - engine/src/StudyStash.Core/Ai/SettingsChat.cs
  - engine/src/StudyStash.Library/LibraryWeb.Inbox.cs
- description: Support chat and diagnostic export are maintenance workflows outside the selected core.
  paths:
  - engine/src/StudyStash.App/Services/SupportAsk.cs
  - engine/src/StudyStash.App/ViewModels/SupportAskModel.cs
- description: Native demo library, widgets, Live Activity, Spotlight and shortcuts integration.
  paths:
  - ios/StudyStashWidgets/
  - ios/Shared/
  - ios/StudyStash/App/DemoLibrary.swift
  - ios/StudyStash/App/SpotlightIndex.swift
  - ios/StudyStash/App/Intents.swift
- description: Terminal service administration and diagnostics beyond setup and updates are operator workflows.
  paths:
  - engine/src/StudyStash.Library/Cli.cs
- description: Marketing and installation website is acquisition content rather than the lecture library.
  paths:
  - site/
- description: Live Canvas reading and file tools offered to AI apps beyond the mirrored material.
  paths:
  - engine/src/StudyStash.Core/ClaudeTools.cs
- description: Downloaded transcription model removal, shortcut customization and local appearance settings are peripheral
    maintenance or presentation choices.
  paths:
  - engine/src/StudyStash.App/Services/Settings.cs
  - engine/src/StudyStash.App/Services/ModelSetting.cs
  - engine/src/StudyStash.App/ViewModels/ShortcutsModel.cs
- description: Configured filesystem folders outside the library and their file search.
  paths:
  - engine/src/StudyStash.App/ViewModels/FolderPickerModel.cs
  - engine/src/StudyStash.Core/Ai/Folders.cs
  - engine/src/StudyStash.Core/Ai/FileIndex.cs
  - engine/src/StudyStash.Library/LibraryWeb.Files.cs
limitations: []
---

# Coverage
