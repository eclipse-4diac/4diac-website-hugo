---
title: 4diac IDE

---

The 3.1 release of the 4diac IDE focuses on modernizing the user interface and providing more powerful tools for managing complex projects and data structures.

### Highlights

#### Struct Member Access & F_MOVE Improvements
Working with complex data structures is now significantly more intuitive. The `F_MOVE` block and other generic variables now fully support **Member Access Pins**.
* **Direct Configuration:** Users can now configure pins for specific struct members directly on `F_MOVE` blocks.
* **Recursive Resolution:** The "Follow/Go-to pin" handlers now recursively resolve member pins, even for deeply nested struct members.
* **Validation:** Connections to member access pins are validated against the underlying struct field type to prevent mapping errors.

#### Enhanced Folder Refactoring
Managing large libraries is now easier with support for **Move and Rename refactoring for folders**. The IDE automatically updates all internal type references and package names for the types contained within the affected folders.

### User Interface & Experience
* **Modernized Look:** A new soft drop shadow has been introduced around the main pages. The interface bars for SubApps and CFBs have been cleaned up by removing unnecessary borders.
* **Seamless Graphical Editing:** 
    * Connections can now be created across different graphical editor boundaries.
    * Re-enabled canvas panning using **Middle Mouse** or **Space + Left Mouse**.
* **Improved Screen Scaling (HiDPI):** Reworked graphical commands to use absolute positions and sizes, ensuring a stable UI on high-resolution displays.
* **Dark Mode Optimizations:** Added dedicated dark mode colors for interface bars, comment figures, and NatTable tree arrows to improve readability.

### Functional Improvements
* **Advanced Event Connection Logic:** When inserting a Function Block into an execution chain, the IDE now intelligently picks the first output event that already has an existing connection as the source.
* **ST Editor Enhancements:** Added language-aware task markers (e.g., TODOs) and common marker types shared across all Structured Text languages.
* **Deployment Initial Values:** A new "Initial Values" tab has been added to deployment launch configurations, including support for member input variables.

### Bug Fixes
* **Stable Type Hashes:** Switched hash generation from XMI to IEC 61499 XML to prevent "unstable" hashes caused by local file references.
* **Security:** Added path normalization before unzipping files to prevent "Zip Slip" vulnerabilities.
