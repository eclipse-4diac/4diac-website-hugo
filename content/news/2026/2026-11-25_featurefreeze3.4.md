---
title: "Eclipse 4diac 3.4 Feature Freeze"
date: 2026-11-25T00:00:00-00:00
categories: ["Releases"]
type: "newsitem"
description: |
  Another three months of development are coming to an end, and Eclipse 4diac 3.4 has reached its feature freeze! Continuing our established three-month release cycle, the release is scheduled for **December 9, 2026**.

  Over the next week and a half, our focus will be on testing, fixing remaining issues, and smoothing out rough edges to make Eclipse 4diac 3.4 as stable and reliable as possible.
fordiacTeamGreating: true
---

## What to Look Forward to in Eclipse 4diac 3.4

This release brings numerous improvements to the engineering, debugging, and operation of distributed IEC 61499 control applications.

### 4diac IDE Highlights

- **Snapshot and Replay Debugging:** New capabilities to inspect and debug function blocks using values and states retrieved from a running control application, together with further improvements to replay debugging.
- **Bulk Editor:** Extended graphical query capabilities for working with large-scale control applications.
- **EtherCAT Engineering:** A new ESI import wizard to simplify the integration of EtherCAT devices.
- **Library Management:** Improved library validation and export workflows, including a new library export preview.
- **Editor Improvements:** Enhanced ECC editing, transition routing, and integrated AsciiDoc documentation support.
- **Modernized Technology Stack:** Migration to Java 25 and Eclipse 2026-12.

### 4diac FORTE Highlights

- **OPC UA:** New function blocks for OPC UA node creation and improved communication reliability.
- **Network Communication:** Parallel TCP connection handling and improved network robustness and diagnostics.
- **Runtime Improvements:** Support for nested delegating connections, improved event handling, and more efficient tracing.
- **Industrial I/O:** Further improvements to EtherCAT and GPIO support.

As part of our ongoing efforts to improve the maintainability of 4diac FORTE, this release also removes several legacy process interface implementations. Users of these interfaces should consult our [earlier announcement](/4diac/news/2026/2026/removing-legacy-process-interfaces-in-4diac-forte/).

## Help Us Make Eclipse 4diac 3.4 Even Better!

The [Eclipse 4diac 3.4 Early Access builds](/4diac/download/) are available, and we encourage you to try them out.

In particular, we would appreciate testing with existing control applications, different hardware platforms, and real-world engineering workflows.
Whether you discover a bug, encounter unexpected behavior, or notice something that could be polished before the release, now is a particularly good time to let us know.

Please report any issues through our GitHub repositories:

- [4diac IDE](https://github.com/eclipse-4diac/4diac-ide/issues)
- [4diac FORTE](https://github.com/eclipse-4diac/4diac-forte/issues)
- [4diac FBE](https://github.com/eclipse-4diac/4diac-fbe/issues)

With the feature freeze in place, development of Eclipse 4diac 3.5 can also begin.

A big thank you to everyone who has contributed to Eclipse 4diac 3.4 through code, testing, bug reports, documentation, and feedback!
