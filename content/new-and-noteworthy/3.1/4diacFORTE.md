---
title: 4diac FORTE

---

The 3.1 release of 4diac FORTE introduces significant architectural cleanups, specifically targeting library modularity and communication efficiency.

### Core Architecture

#### IEC 61131-3 Function Library Modularization
The standard function library has undergone a major refactoring. Functions are now split into individual headers. This modularity:
* Improves compile times.
* Allows for more granular inclusion of only the required math and conversion functions.
* Cleanly separates math definitions from conversion logic.

#### Memory & Performance Optimizations
* **FreeRTOS Integration:** Optimized thread stack initialization to prevent unnecessary memory allocation. In FreeRTOS, the stack is now initialized as `nullptr` when only the size is required, saving valuable RAM on embedded targets.
* **String Efficiency:** Migrated several internal helpers to use `std::string_view` to avoid temporary string allocations during object lookup and creation.

### OPC UA & Communication
* **Alarm & Condition Support:** Refactored the OPC UA Alarm state fetching and object creation to better support SIFB-based alarm handling.
* **Namespace Handling:** Updated the namespace delimiter for struct type handling to ensure better compatibility with standard OPC UA clients.
* **Startup Diagnostics:** Added detailed help messages when FORTE is unable to create a device due to missing shared libraries or linker flag issues.

### New Function Blocks & Logic
* **New Blocks:** Added `SPLIT_DWORD_INTO_BYTES` and updated `ASSEMBLE_DWORD_FROM_BYTES` for consistent 4-byte handling.
* **Composite FB Enhancements:** Added support for **delegating connections** within Composite FBs, including improved handling of SIFBs inside CFBs and outgoing events.
* **Generic Array Handling:** Improved `VALUES2ARRAY` and `ARRAY2VALUES` logic for updating InOut array bounds from reference values with variable bounds.

### Releng & Documentation
* **CI/CD:** GitHub workflows now run on all branches to ensure stability across the development lifecycle.
* **Doxygen:** Major cleanup of the Doxyfile and documentation paths for the standard function library (`stdfblib`).
