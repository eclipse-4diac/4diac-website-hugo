---
title: 4diac IDE
description: TBA
---



### Bulk Editor

- Added first prototype of the Bulk Query Language inside the BulkEditor



### Connection Usability

- Added a more aggressive delete of connections, which deletes connections all the way to the next FB
- Reworked reconnect to merge connections if possible
  - When a connection is dragged to a pin that already has a connection, connections are merged for their shared path



### Bug Fixes

- Pin names are now case insensitive
- Error FBs/Pins are now created correctly for connections with missing source/destination



# Deleting Function Blocks Has Never Been This Satisfying

You're deep in a Function Block network, re-architecting your distributed control application, and it's time to clean house. You select the blocks that no longer serve the design, hit delete, and… they just vanish. Functional, sure — but where's the fun in that?

## A Small Spark of Joy in the Editor

A new contribution to Eclipse 4diac IDE adds an optional visual explosion animation that plays whenever you delete Function Blocks or Connections in the Application Editor. Instead of elements silently disappearing from the canvas, they burst apart in a brief, satisfying particle effect before fading out.

<video src="./resources/explosion_video.webm" controls=""></video>

It's a small touch — but once you've seen it, plain deletion feels strangely incomplete.
The feature is entirely optional and can be toggled off for those who prefer their deletions quiet and dignified.

Happy deleting!
