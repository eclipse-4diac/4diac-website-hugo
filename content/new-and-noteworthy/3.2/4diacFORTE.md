---
title: 4diac FORTE
description: Improved runtime performance, extended data type support, and upgraded OPC UA connectivity.
---

- Improve performance and binary size for floating-point formatting
- Add support for `ANY_STRUCT` and `ANY_DERIVED` data types
- Fix through connections in Composite FBs
- Display actual port being used when Forte is started with port 0
### OPC UA
- Upgraded the OPC UA stack to [open26541](https://open62541.org/) v1.5.4
- Reorganized OPC UA Comlayer for non-amalgamation open62541 builds
