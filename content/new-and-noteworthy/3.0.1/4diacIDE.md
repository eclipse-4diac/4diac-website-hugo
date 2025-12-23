---
title: 4diac IDE

---

4diac IDE 3.0.1 is a maintenance release focusing on improved robustness, correctness, and usability. This page highlights the most important **user-visible changes** since version 3.0.0.



### Graphical Editors & HiDPI Support

- Corrected zoom and scaling when adjusting bendpoints and positioning function blocks
- Improved behavior on high-DPI displays, including Windows with GEF Classic HiDPI support

### Structured Text (ST) Editor

- Fixed missing-variable quick fixes to generate valid non-generic types
- Resolved potential null-pointer exceptions for incompatible types
- Improved handling of equals-checks in variable declarations

### Adapter Handling & Model Consistency

- Adapter type changes are now propagated correctly to all editors
- Fixed incorrect error event pins when changing adapter types, especially in composite function blocks

### UI & Editor Stability

- Debug view now handles empty states without exceptions
- Outline pages in multi-page editors are reliably disposed and re-created
- Equality checks in tables now work correctly for empty cells

### Additional Fixes

- Added validation in data type selection dialogs
- Improved parsing of array and struct values
- Updated documentation and cleaned up UI message handling
