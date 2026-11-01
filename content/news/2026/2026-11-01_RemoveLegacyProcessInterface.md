---
title: "Removing Legacy Process Interfaces in 4diac FORTE"
date: 2026-11-01T00:00:00-00:00
categories: ["4diac FORTE"]
type: "newsitem"
description: |
  To keep 4diac FORTE maintainable and focus development resources on active features, the Eclipse 4diac project is preparing to remove legacy process interface implementations from the 4diac FORTE codebase.
fordiacTeamGreating: true
---

### Background

The legacy process interface codebase has been broken and non-compiling for the past four releases. Given that no issues or pull requests have been submitted for these interfaces during this period, they are no longer in active use. 

Attempting to repair and maintain these obsolete implementations takes focus away from improving 4diac FORTE and advancing the modern process interface framework.

### Impact on Users

* **Current & New Projects:** No impact. Active developments should continue using the current process interface architecture.
* **Legacy Integrations:** Any setups still relying on old process interfaces will need to transition to the current implementation model.

### Get Involved

Do you depend on a specific legacy process interface and need to keep it alive? 

If a legacy interface is critical to your setup, please get in touch! We welcome community collaboration to help bring vital interfaces over to the new process interface architecture.

Please leave your comments, vote, or raise any concerns directly on [GitHub Issue #1136](https://github.com/eclipse-4diac/4diac-forte/issues/1136).
