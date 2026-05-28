---
title: 4diac IDE

---

### User Interface & Usability Enhancements

 - New grid for all graphical editors that reduces visual clutter to improve focus on content
 - Modernized look of Interface Editor:
   - Cleaner alignment of comments and data types
   - Connections follow type colors to be in line with Function Block Network editor
 - Mapped Function Blocks are now shown with a device-colored bar at the bottom of the block
 - Modernized look of ECC editor:
   - Color scheme adjusted to overall IEC 61499 colors (i.e. events and data connections)
   - Improved state representation with cleaner action lists
   - Smoother splines for transitions
 - Added member access pins for all FB instances
 - Added unified wizard to manage project libraries
 - Removed *Affected Types* dialog when saving types

### New and changed validations
 - An internal FB may not have the same name as a pin of the surrounding type or instance
 - An internal FB in a Simple or Basic FB must be a Simple, Basic, or Service Interface FB
 - Warn for unused FB and SubApp instances with no incoming event connections
 - Validate additional cases of incompatible types with generic inputs or outputs
 - Optionally validate multiple event output connections leading to undefined execution order
 - Variables may now have the same name as a data type

### ST Editor
 - Remove `ALGORITHM` and `METHOD` blocks when saving algorithms in FB types for improved compatibility with other IEC 61499 tools
 - Extract method refactoring now uses the exact selection
 - Update ST code during copy refactoring

### Deployment and Monitoring
 - Show resource status in *Debug* view
 - No longer watch internal FBs or variables by default
 - Separated OPC UA deployment into its own optional feature
 - Type hash now only considers Negate and Retain attributes