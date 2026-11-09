---
title: "Planned IEC 61499 Type Hash Changes in Eclipse 4diac 3.5"
date: 2026-11-09T00:00:00-00:00
categories: ["4diac IDE"]
type: "newsitem"
description: |
  We are preparing an update to the IEC 61499 type hash algorithm for Eclipse 4diac 3.5. 
  This may affect even unchanged types and will require re-exporting FB types.
fordiacTeamGreating: true
---

Eclipse 4diac uses type hashes to detect functional or structural mismatches of IEC 61499 types between 4diac IDE and 4diac FORTE.

During our ongoing work on [IEC 61499 XSDs](https://github.com/eclipse-4diac/4diac-documentation/pull/110) and investigations into recently discovered bugs (e.g., [#3112](https://github.com/eclipse-4diac/4diac-ide/pull/3112)), we identified several issues in the current type hash algorithm. 
Addressing these issues will require backward-incompatible changes to the resulting hash values.

To avoid introducing incompatible changes across multiple releases, we plan to collect and coordinate all known and foreseeable hash-related changes and introduce them together with a **version bump of the type hash algorithm in Eclipse 4diac 3.5**.

## What Does This Mean for Users?

**No action is required at this time.**

With Eclipse 4diac 3.5, type hashes may change even for IEC 61499 types that have not been modified. Whether a particular type is affected depends on the language and modeling features it uses.

As a consequence, users will need to **re-export their FB types** to ensure that the type hashes used by 4diac IDE and 4diac FORTE remain consistent.

To prevent unintended hash changes before the planned update, we are also introducing a dedicated [hash regression test suite](https://github.com/eclipse-4diac/4diac-ide/pull/3125).

## Follow the Changes and Join the Discussion

We have created a dedicated GitHub issue to coordinate the changes, collect related fixes, and track the preparation for Eclipse 4diac 3.5.

The changes are being collected in a dedicated [feature branch](https://github.com/eclipse-4diac/4diac-ide/tree/libelem-hash-v3).

For further details, updates, or to raise any concerns, please visit the [type hash update planning issue](https://github.com/eclipse-4diac/4diac-ide/issues/3175).

We welcome feedback, particularly from users maintaining IEC 61499 type libraries or integrations with 4diac FORTE.
