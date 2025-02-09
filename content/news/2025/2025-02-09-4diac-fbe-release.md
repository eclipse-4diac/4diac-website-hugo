---
title: "Eclipse 4diac FORTE Build Environment Release beta-2025-02"
slug: "Eclipse 4diac FBE Release beta-2025-02"
date: 2025-02-09T14:00:00-00:00
categories: ["4diacfbe"]
type: "newsitem"
description: "Release announcement for Eclipse 4diac FBE beta-2025-02."
fordiacTeamGreating: true
---

## Eclipse 4diac FORTE Build Environment (FBE) Released!

4diac FBE has been part of the Eclipse 4diac project for a while, and several
users have started using it and providing valuable feedback. Today is the very
first official (pre-)release, containing lots of quality-of-life improvements
to make the 4diac FBE experience as nice as possible.

To download this release, head over to https://github.com/eclipse-4diac/4diac-fbe/releases
and get `4diac-fbe-beta-2025-02.zip`. Make sure you get the correct file, do NOT fetch the
source code archives. To install, extract to a suitable folder and run `compile.cmd`. Yes,
Linux users also run `compile.cmd`. Read `README.md` for more details.

Notable changes:

* Change to a single unified build script `compile.cmd` for all platforms
* Much improved progress output during install and builds: Progress indicators for downloads
  and build processes.
* Much improved build logging. This should make future troubleshooting much easier.
* Improved detection of common install failures. Read the error messages :-)
* Fixes for the latest Eclipse 4diac FORTE changes to open62541
* Fixes for open62541 on win32

If no serious bugs are discovered, this beta release will be upgraded to a full release in a few weeks.

Many thanks to all contributors and users for their work and their feedback!
