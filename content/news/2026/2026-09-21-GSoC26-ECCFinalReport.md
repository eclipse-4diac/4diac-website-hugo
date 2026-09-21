---
title: "GSoC 2026 Final Report: Improving the ECC Editor"
date: 2026-09-21 00:00:00 +0000
categories: 
  - GSoC
type: newsitem
description: "Google Summer of Code 2026 final report by Vikash Kumar Sinha, describing improvements to the ECC editor in 4diac IDE, including state placement, transition routing, connection anchors, breakpoint support, and bendpoint preservation during state movement."
---

## Project Information

| Field | Details |
|---|---|
| **Project Name** | Improving the ECC Editor in Eclipse 4diac IDE |
| **Organization** | Eclipse Foundation |
| **Project** | Eclipse 4diac IDE |
| **Repository** | [eclipse-4diac/4diac-ide](https://github.com/eclipse-4diac/4diac-ide) |
| **Repository Description** | Eclipse 4diac IDE is an open-source engineering tool for IEC 61499-based distributed automation systems. |
| **Contributor** | Vikash Kumar Sinha |
| **GitHub Username** | [vikash1703](https://github.com/vikash1703) |
| **Mentor** | Alois Zoitl |
| **GSoC Year** | 2026 |
| **Primary Technologies** | Java, Eclipse RCP, GEF, IEC 61499 Model |
| **Main Module** | ECC Editor |
| **Merged Pull Requests** | 16 |

---

# 1. Executive Summary

During my Google Summer of Code project with the Eclipse Foundation, I worked on improving the Execution Control Chart (ECC) editor of Eclipse 4diac IDE.

Eclipse 4diac IDE is an open-source engineering environment for developing IEC 61499-based distributed automation systems. The ECC editor is an important component of the IDE because it allows users to visually design execution control logic using states and transitions.

My work focused on improving the reliability, usability, maintainability, performance, and model consistency of the ECC editor.

The major areas of work included:

- Correcting ECC state placement under different zoom levels
- Separating model coordinates from screen coordinates
- Removing unnecessary UI dependencies from model commands
- Improving transition routing
- Implementing connection anchors for ECC states
- Fixing transition spline rendering
- Improving edge-direction calculation
- Fixing self-loop transitions
- Adding ECC debugging breakpoint support
- Optimizing connection-anchor calculations
- Adding inline ECC state creation
- Preserving transition bendpoints when a state is moved

During the project, 16 of my pull requests were merged into the Eclipse 4diac IDE repository. These contributions improved both the internal architecture and the user-facing behavior of the ECC editor.

---

# 2. Summary of Contributions

The following 16 pull requests were merged during the project:

1. PR #2189 — Clean CreateECStateCommand to remove screen coordinate dependency
2. PR #2209 — Fix EC state placement under zoom
3. PR #2226 — Fix zoom-aware coordinate translation in NewStateAction
4. PR #2269 — Remove UI dependency from CreateTransitionCommand
5. PR #2369 — Implement ECStateConnectionAnchor
6. PR #2421 — Fix ECC transition splines
7. PR #2430 — Refactor edge direction
8. PR #2445 — Fix edge direction aspect ratio
9. PR #2495 — Fix ECC new router
10. PR #2526 — Fix ECC self-loop
11. PR #2548 — Fix bug 2546
12. PR #2568 — Implement EvaluatorModelBreakpoint for ECC debugging
13. PR #2573 — Add support for ECC state model breakpoints
14. PR #2611 — Fix ECC anchor stream optimization
15. PR #2884 — Create ECC state on commit of the inline editor
16. PR #2897 — Adjust transition bendpoints when a state is moved

---

# 3. Detailed Contributions

## 3.1 PR #2189 — Clean CreateECStateCommand to remove screen coordinate dependency

[PR #2189](https://github.com/eclipse-4diac/4diac-ide/pull/2189)

This pull request removed screen-coordinate conversion from **CreateECStateCommand**.

The command was changed to accept a Position object directly and operate using IEC 61499 model coordinates. This improved the separation between the graphical user interface and the model layer.

The change resulted in:

- A cleaner command interface
- Better separation between model logic and UI logic
- Reduced dependency on graphical viewer objects
- More predictable state creation behavior
- Better support for testing and reuse

## 3.2 PR #2209 — Fix EC state placement under zoom

[PR #2209](https://github.com/eclipse-4diac/4diac-ide/pull/2209)

This pull request fixed incorrect ECC state placement when creating a state while the editor was zoomed.

The mouse location was previously used without properly compensating for the current zoom factor. The coordinate calculation was updated to account for zoom before creating the state.

The behavior was tested under:

- 100% zoom
- Zoomed-in views
- Zoomed-out views
- State creation followed by transition creation

This made state creation more accurate and predictable.

## 3.3 PR #2226 — Fix zoom-aware coordinate translation in NewStateAction

[PR #2226](https://github.com/eclipse-4diac/4diac-ide/pull/2226)

This pull request improved coordinate translation when creating an ECC state through the right-click context menu.

The previous implementation manually calculated coordinates using viewport offsets and zoom factors. The implementation was changed to use GEF's built-in **translateToRelative()** method.

This correctly handles:

- Zoom level
- Viewport offsets
- Scrolling
- Figure-relative coordinates
- Diagram translation

The change reduced duplicated coordinate-transformation logic and made the implementation better integrated with Eclipse GEF.

## 3.4 PR #2269 — Remove UI dependency from CreateTransitionCommand

[PR #2269](https://github.com/eclipse-4diac/4diac-ide/pull/2269)

This pull request removed UI and screen-coordinate dependencies from **CreateTransitionCommand**.

The following fields and methods were removed:

- sourceLocation
- destLocation
- Viewer references
- setSourceLocation()
- setDestinationLocation()
- setViewer()

The transition bendpoint calculation now uses the model positions of the source and destination states directly.

Related callers were updated in:

- TransitionNodeEditPolicy
- ReconnectTransitionCommand
- ECCEditorEditDomain

This improved the separation between model commands and graphical editor state.

## 3.5 PR #2369 — Implement ECStateConnectionAnchor

[PR #2369](https://github.com/eclipse-4diac/4diac-ide/pull/2369)

This pull request implemented a dedicated connection-anchor mechanism for ECC states.

Connection anchors determine where transitions connect to states. Correct anchor calculation is important for:

- Clean transition paths
- Correct transition direction
- Avoiding overlapping connections
- Supporting self-loops
- Supporting spline rendering
- Improving routing stability

The implementation considered state boundaries, transition direction, source and target positions, and ECC routing requirements.

<img width="1316" height="897" alt="image" src="https://github.com/user-attachments/assets/2817d9bd-4180-47e4-9cca-fd9532856c6c" />

## 3.6 PR #2421 — Fix ECC transition splines

[PR #2421](https://github.com/eclipse-4diac/4diac-ide/pull/2421)

This pull request fixed problems related to ECC transition spline rendering and routing.

The changes improved:

- Curve generation
- Transition path layout
- Connection behavior
- Visual consistency
- Interaction with state geometry

The resulting ECC diagrams became easier to read, particularly when multiple transitions were present.

<img width="1466" height="768" alt="image" src="https://github.com/user-attachments/assets/d95a5ffe-3c5f-45cc-9c75-5afe352b4925" />

## 3.7 PR #2430 — Refactor edge direction

[PR #2430](https://github.com/eclipse-4diac/4diac-ide/pull/2430)

This pull request refactored the logic used to determine edge direction.

Edge direction is important for selecting appropriate connection points and routing paths. The refactoring made direction handling more consistent and reduced duplicated logic.

This created a cleaner foundation for:

- Connection-anchor calculations
- Transition routing
- Aspect-ratio handling
- Spline generation
- Direction-dependent rendering

## 3.8 PR #2445 — Fix edge direction aspect ratio

[PR #2445](https://github.com/eclipse-4diac/4diac-ide/pull/2445)

This pull request fixed edge-direction calculations involving aspect ratio.

When the horizontal and vertical distances between states were significantly different, the direction calculation could select an inappropriate edge. The updated implementation considers the relative aspect ratio between states.

This improved connection placement for:

- Mostly horizontal transitions
- Mostly vertical transitions
- Diagonal transitions
- States positioned at different distances

## 3.9 PR #2495 — Fix ECC new router

[PR #2495](https://github.com/eclipse-4diac/4diac-ide/pull/2495)

This pull request fixed routing problems in the new ECC transition router.

The changes improved the handling of:

- State locations
- Connection anchors
- Edge directions
- Transition geometry
- ECC diagram layout

The router now produces more stable and understandable transition paths, especially in diagrams containing multiple states and transitions.

## 3.10 PR #2526 — Fix ECC self-loop

[PR #2526](https://github.com/eclipse-4diac/4diac-ide/pull/2526)

This pull request fixed the handling and rendering of ECC self-loop transitions.

A self-loop begins and ends at the same state and requires special routing logic. Without dedicated handling, a self-loop can overlap the state or be rendered as a normal connection.

The routing and rendering behavior was corrected so that self-loop transitions are represented properly.

<img width="392" height="394" alt="image" src="https://github.com/user-attachments/assets/21eabb7f-6109-4c76-82a4-05b4592989fd" />

## 3.11 PR #2548 — Fix bug 2546

[PR #2548](https://github.com/eclipse-4diac/4diac-ide/pull/2548)

This pull request addressed the ECC-related issue tracked as bug 2546.

The fix was applied to the 3.2.x maintenance branch and targeted the specific incorrect behavior reported in the issue. This helped improve the stability of the maintained Eclipse 4diac release line.

## 3.12 PR #2568 — Implement EvaluatorModelBreakpoint for ECC debugging

[PR #2568](https://github.com/eclipse-4diac/4diac-ide/pull/2568)

This pull request introduced **EvaluatorModelBreakpoint** for ECC debugging.

The implementation added a model-level representation of breakpoints. This allows breakpoint information to be connected to ECC model elements rather than only to visual editor objects.

Model-level breakpoints:

- Remain associated with the underlying ECC model
- Are less dependent on the current UI state
- Integrate with debugging infrastructure
- Support runtime evaluation workflows

## 3.13 PR #2573 — Add support for ECC state model breakpoints

[PR #2573](https://github.com/eclipse-4diac/4diac-ide/pull/2573)

This pull request extended the debugging work by adding breakpoint support for ECC state model elements.

Users need to stop or inspect execution at specific ECC states while debugging function block behavior. The implementation connected ECC states with the breakpoint infrastructure.

This contribution improved the debugging experience by allowing users to reason about execution directly through the ECC model.

<img width="1280" height="802" alt="image" src="https://github.com/user-attachments/assets/76eb8e27-db15-4c0c-ac29-8ac43aba99de" />

## 3.14 PR #2611 — Fix ECC anchor stream optimization

[PR #2611](https://github.com/eclipse-4diac/4diac-ide/pull/2611)

This pull request optimized connection-anchor calculation using Java Streams.

The previous implementation used separate intermediate collections for incoming and outgoing transitions. The updated implementation combines these transitions more efficiently.

The changes helped to:

- Avoid unnecessary intermediate lists
- Reduce memory overhead
- Handle mixed transition collections consistently
- Prevent overlapping transitions on the same state edge

## 3.15 PR #2884 — Create ECC state on commit of the inline editor

[PR #2884](https://github.com/eclipse-4diac/4diac-ide/pull/2884)

This pull request introduced inline creation of ECC states.

The new workflow allows the user to:

1. Double-click an empty area of the ECC canvas.
2. Open an inline text editor.
3. Enter or edit the state name.
4. Commit the text to create the state.
5. Cancel the edit without modifying the model.

The state is created only after the user commits the name. This makes state creation more direct and intuitive.

## 3.16 PR #2897 — Adjust transition bendpoints when a state is moved

[PR #2897](https://github.com/eclipse-4diac/4diac-ide/pull/2897)

This pull request preserves transition layout when an ECC state is moved.

When a state is dragged to a new position, the connected transitions may contain bendpoints that define their routing. If the state moves but the bendpoints remain unchanged, the transition paths can become distorted.

The implementation:

- Detects movement of the ECC state
- Calculates the difference between old and new positions
- Finds connected transitions
- Applies the same movement delta to their bendpoints
- Updates the model using SetPositionCommand
- Persists the updated bendpoint positions in the XML model

This keeps connected transitions visually aligned with the moved state and preserves the relative layout of the ECC diagram.

---

# 4. Pull Request Summary

| No. | PR | Title | Main Contribution |
|---|---|---|---|
| 1 | [#2189](https://github.com/eclipse-4diac/4diac-ide/pull/2189) | Clean CreateECStateCommand to remove screen coordinate dependency | Removed screen-coordinate dependency from state creation command. |
| 2 | [#2209](https://github.com/eclipse-4diac/4diac-ide/pull/2209) | Fix EC state placement under zoom | Corrected state placement at different zoom levels. |
| 3 | [#2226](https://github.com/eclipse-4diac/4diac-ide/pull/2226) | Fix zoom-aware coordinate translation in NewStateAction | Used GEF coordinate translation for reliable state creation. |
| 4 | [#2269](https://github.com/eclipse-4diac/4diac-ide/pull/2269) | Remove UI dependency from CreateTransitionCommand | Removed viewer and screen-coordinate dependencies from transition commands. |
| 5 | [#2369](https://github.com/eclipse-4diac/4diac-ide/pull/2369) | Implement ECStateConnectionAnchor | Improved connection points and transition routing around ECC states. |
| 6 | [#2421](https://github.com/eclipse-4diac/4diac-ide/pull/2421) | Fix ECC transition splines | Improved transition spline rendering and path geometry. |
| 7 | [#2430](https://github.com/eclipse-4diac/4diac-ide/pull/2430) | Refactor edge direction | Refactored edge-direction calculation and handling. |
| 8 | [#2445](https://github.com/eclipse-4diac/4diac-ide/pull/2445) | Fix edge direction aspect ratio | Corrected direction decisions using relative aspect ratio. |
| 9 | [#2495](https://github.com/eclipse-4diac/4diac-ide/pull/2495) | Fix ECC new router | Improved the behavior of the new ECC transition router. |
| 10 | [#2526](https://github.com/eclipse-4diac/4diac-ide/pull/2526) | Fix ECC self-loop | Corrected self-loop transition handling and rendering. |
| 11 | [#2548](https://github.com/eclipse-4diac/4diac-ide/pull/2548) | Fix bug 2546 | Fixed an ECC-related bug in the 3.2.x maintenance branch. |
| 12 | [#2568](https://github.com/eclipse-4diac/4diac-ide/pull/2568) | Implement EvaluatorModelBreakpoint for ECC debugging | Added the model-level breakpoint foundation for ECC debugging. |
| 13 | [#2573](https://github.com/eclipse-4diac/4diac-ide/pull/2573) | Add support for ECC state model breakpoints | Added breakpoint support for ECC state model elements. |
| 14 | [#2611](https://github.com/eclipse-4diac/4diac-ide/pull/2611) | Fix ECC anchor stream optimization | Optimized anchor calculation and reduced intermediate collections. |
| 15 | [#2884](https://github.com/eclipse-4diac/4diac-ide/pull/2884) | Create ECC state on commit of the inline editor | Added inline ECC state creation with commit/cancel behavior. |
| 16 | [#2897](https://github.com/eclipse-4diac/4diac-ide/pull/2897) | Adjust transition bendpoints when a state is moved | Preserved connected transition layout when a state is moved. |

---

# 5. Future Scope

Possible future work includes:

1. Adding more automated tests for ECC routing and coordinate transformations.
2. Improving visual feedback while moving states.
3. Providing better automatic layout for large ECC diagrams.
4. Supporting more advanced transition-routing strategies.
5. Improving breakpoint visualization inside the ECC editor.
6. Adding tests for self-loop and multi-transition scenarios.
7. Improving undo and redo behavior for transition geometry changes.
8. Providing better accessibility and keyboard support for inline editing.
9. Improving performance for very large ECC models.
10. Adding more documentation for ECC editor architecture and routing behavior.

---

# 6. Conclusion

During my GSoC project, I worked on improving the ECC editor of Eclipse 4diac IDE. My contributions covered both user-facing features and internal architectural improvements.

The work improved:

- State creation
- Zoom-aware positioning
- Coordinate transformation
- Transition routing
- Connection anchors
- Spline rendering
- Edge direction
- Self-loop handling
- Debugging breakpoints
- Anchor calculation performance
- Inline state creation
- State movement and bendpoint preservation

A total of 16 pull requests were merged into the Eclipse 4diac IDE repository. These changes improved the reliability, maintainability, performance, usability, and model consistency of the ECC editor.

The project also helped me gain valuable experience in Java, Eclipse plug-in development, GEF-based graphical editors, model-driven engineering, debugging infrastructure, industrial automation, GitHub collaboration, and open-source software development.

I am grateful to my mentor, Alois Zoitl, the Eclipse 4diac community, and the Eclipse Foundation for their guidance, reviews, and support throughout the project.

---

# 7. Important Links

## Repository

[Eclipse 4diac IDE](https://github.com/eclipse-4diac/4diac-ide)

## Contributor Profile

[Vikash Kumar Sinha — GitHub Profile](https://github.com/vikash1703)

## Merged Pull Requests

- [PR #2189](https://github.com/eclipse-4diac/4diac-ide/pull/2189)
- [PR #2209](https://github.com/eclipse-4diac/4diac-ide/pull/2209)
- [PR #2226](https://github.com/eclipse-4diac/4diac-ide/pull/2226)
- [PR #2269](https://github.com/eclipse-4diac/4diac-ide/pull/2269)
- [PR #2369](https://github.com/eclipse-4diac/4diac-ide/pull/2369)
- [PR #2421](https://github.com/eclipse-4diac/4diac-ide/pull/2421)
- [PR #2430](https://github.com/eclipse-4diac/4diac-ide/pull/2430)
- [PR #2445](https://github.com/eclipse-4diac/4diac-ide/pull/2445)
- [PR #2495](https://github.com/eclipse-4diac/4diac-ide/pull/2495)
- [PR #2526](https://github.com/eclipse-4diac/4diac-ide/pull/2526)
- [PR #2548](https://github.com/eclipse-4diac/4diac-ide/pull/2548)
- [PR #2568](https://github.com/eclipse-4diac/4diac-ide/pull/2568)
- [PR #2573](https://github.com/eclipse-4diac/4diac-ide/pull/2573)
- [PR #2611](https://github.com/eclipse-4diac/4diac-ide/pull/2611)
- [PR #2884](https://github.com/eclipse-4diac/4diac-ide/pull/2884)
- [PR #2897](https://github.com/eclipse-4diac/4diac-ide/pull/2897)

## Signature

- **Contributor:** Vikash Kumar Sinha
- **Mentor:** Alois Zoitl
- **Organization:** Eclipse Foundation
- **Project:** Eclipse 4diac IDE
- **Date:** September 20, 2026
