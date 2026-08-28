---
title: "Eclipse 4diac 3.3 Feature Freeze"
date: 2026-08-27T00:00:00-00:00
categories: ["Releases"]
type: "newsitem"
description: |
  The feature freeze for the upcoming Eclipse 4diac 3.3 release is now complete, and we are officially entering the stabilization phase.
  
  Our focus over the coming weeks is strictly on testing, fixing remaining issues, and polishing the release ahead of the **September 9, 2026** launch. This release brings substantial new capabilities to both 4diac IDE and 4diac FORTE to improve the diagnosis, visualization, and deployment of distributed IEC 61499 applications.
fordiacTeamGreating: true
---


### 4diac IDE Highlights

- **Replay Debugging:** A powerful new toolset to record, replay, and navigate execution traces across multiple devices. Complete with a dedicated timeline view, state comparison, and step-by-step undo/redo, this significantly simplifies diagnosing complex timing and sequencing issues.
- **Event Sequence View:** A brand-new dedicated visual representation for defining, reviewing, and testing function block service sequences with intuitive drag-and-drop reordering.
- **Library Management Infrastructure:** Important foundational improvements including a redesigned manifest editor, a new Manage Library Wizard, and direct library import from the New Project wizard.
    

### 4diac FORTE Highlights

- **Expanded Industrial Platform Support:** Upgraded support for Wago and RevolutionPi, including new Wago 750-636 register communication and a newly added EtherCAT fieldbus communication support.
- **Enhanced Monitoring:** New monitoring capabilities specifically for struct members.
- **Robust Deployment:** Hardened deployment command parsing.

### We need your help!

The Eclipse 4diac 3.3 Early Access build is now available through the [download page](/4diac/download). We highly encourage all users to download it, try the new features in your environments, and provide feedback. Community testing is critical to making the final release as stable as possible. If you encounter any bugs, please report them directly on the [issue trackers](https://github.com/eclipse-4diac).

With the 3.3 feature freeze complete, the `develop` branches are now open for contributions targeting the upcoming Eclipse 4diac 3.4 release.

Thank you to everyone who has contributed to Eclipse 4diac 3.3 through code, testing, bug reports, and feedback. Your contributions help make Eclipse 4diac better with every release!