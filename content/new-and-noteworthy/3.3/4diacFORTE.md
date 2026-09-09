---
title: 4diac FORTE
description: |
  4diac FORTE 3.3 introduces EtherCAT support as a major new feature and brings a broad set of improvements across industrial I/O support, OPC UA, runtime behavior, and internal architecture.
---

4diac FORTE 3.3 introduces **EtherCAT support** as a major new feature and brings a broad set of improvements across industrial I/O support, OPC UA, runtime behavior, and internal architecture.

### EtherCAT Support (new)

4diac FORTE 3.3 adds EtherCAT support with the first set of required building blocks:

- Core EtherCAT integration
- Initial EtherCAT IO function blocks
- Foundation for further EtherCAT expansion in upcoming releases

### I/O Updates

I/O support for industrial platforms and devices has been extended and fixed:

- Wago and RevolutionPi I/O support updated to latest I/O infrastructure
- Register communication for Wago 750-636 module

### OPC UA Improvements

OPC UA functionality has been improved in deployment, runtime handling, monitoring, and validation:

- Fixes for query-type command handling in deployment
- Correct SecureChannel state reporting in client callbacks
- OPC UA enabled on Linux CI workflows
- Regenerated UA types for system test alignment
- Monitoring support for struct members

### Runtime fixes and stability improvements

- Unique IDs for adapter instances to prevent event overlap
- Timer-related bug fixes
- Regenerated RampLimitFS implementation for corrected INIT behavior

### Management command refactoring

The management command subsystem was reworked and cleaned up to better and more correctly handle wrong or malicious commands:

- Command parsing restructured
- Command execution separated from parsing
- Additional parser rework for consistency and maintainability

