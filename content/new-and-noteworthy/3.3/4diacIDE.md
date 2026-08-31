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

