---
title: 4diac IDE
description: |
  New ways to inspect and reorganize event networks, create advanced Bulk Editor queries, validate projects with custom rules, and work more safely with structured data, dependencies, replay traces, and broken model content.
---

4diac IDE 3.3 provides new ways to inspect and reorganize event networks, create advanced Bulk Editor queries, validate projects with custom rules, and work more safely with structured data, dependencies, replay traces, and broken model content.

### Event Flow Analysis and Editing

A new **Event Sequence** view provides a structural outline of event connections in function block networks. This makes event chains easier to understand, review, and explain without manually tracing every connection in the editor.

*Highlights:*

- visual event sequence overview for FB networks
- sequence ordering and event relationships at a glance
- support for nested untyped subapplications
- double-click navigation back to the network editor
-  Drag-and-drop reordering in the Event Sequence view allows direct reordering of function blocks using drag and drop, which automatically updates the affected event connections.


### Replay Debugging Enhancements

- Replay across multiple devices  
  Replay Debugging now supports sessions spanning multiple devices. Users can select only the required resources from each device and configure replay options independently.
- Replay Debugging has gained several workflow improvements that make trace analysis more practical and more efficient.
- Replay sessions are now easier to explore without risking accidental damage to imported traces.

### Bulk Editor and Query Authoring

The Bulk Editor has been reworked into a clearer multi-page workflow. Search configuration, result editing, and advanced query design are now separated into dedicated pages, helping users focus on one task at a time.

*Highlights:*

- **Controls** page for search setup
- **Result** page for editing matching elements
- **Query** page for advanced search construction

### Project Validation and Model Quality

#### Project-level OCL Validation

Introduction of a project-level OCL validation builder. Projects can now define custom OCL constraints that are evaluated automatically during builds, with violations reported as markers in the Problems view. This makes it easier for teams to enforce project-specific modeling rules across project content and referenced libraries.

Highlights:

- OCL validation can be enabled or disabled per project
- constraints can be loaded from the project and its build path
- violations appear as standard Eclipse markers
- obsolete OCL markers are removed when validation is disabled

#### Improved Validation and Cleanup for Interfaces and Connections

Validation and cleanup workflows have been extended to make model maintenance easier. Unused pins in CFB types and SubApps can now be detected automatically, and cleanup actions help resolve such issues directly from validation output.

Highlights:

- validation for unused interface pins
- quick fix support for deleting unused pins
- improved consistency between collision feedback and collision validation
- better cleanup behavior for obsolete validation markers


### Function Block and ECC Editing

#### Event Actions Editor for Simple FBs

Simple FB types now have a dedicated **Event Actions** section for assigning algorithms and output events to input events in a structured table-based UI. This makes simple FB behavior easier to configure graphically.

*Highlights:*

- assign one or multiple actions per input event
- select algorithms and output events in a dedicated UI
- reorder and delete actions directly in the property tab

#### ECC Editor Improvements

The ECC editor has been improved in several areas, making it easier to understand and debug basic FB behavior.

*Highlights:*

- breakpoints can now be placed directly on ECC states
- self-transitions are displayed more clearly as loops
- a graphical outline improves ECC navigation and orientation

### Structured Data, Configuration, and Refactoring

- **Unified Configuration for Configurable FBs**  
  Configurable FBs, multiplexers, and demultiplexers can now be configured through the standard **Instance** property tab. This reduces fragmentation and makes configuration more consistent across block types.

- **Better Structured and Array Value Editing**  
  Editing large structured and array initial values is now more efficient. Instead of expanding and storing complete values, 4diac can preserve only the differences from defaults.

- **Improved Refactoring Reliability**  
  Refactoring workflows were enhanced to better preserve dependent references and related configuration during copy and rename operations.

  *Highlights:*
  - improved rename handling for structured members
  - safer copy and rename refactorings
  - better update behavior for dependent references, values, and connections

### Project and Library Management

- **Improved project creation with library import**  
The New 4diac Project wizard can now import required libraries directly during project creation, reducing setup effort for new projects.
- Redesigned manifest and dependency handling  
Library dependency management has been improved through a redesigned dependency page and better refresh behavior after builds.

  *Highlights:*
  - easier dependency maintenance
  - improved refresh after library build
  - clearer validation and editing workflows

- **Better remote library and GitLab configuration**  
  Remote library access is more robust and easier to automate in development and CI environments.

  *Highlights:*
  - Ant task for GitLab endpoint configuration
  - migration from legacy GitLab settings to endpoint-based configuration
  - invalid remote versions are skipped instead of blocking valid downloads

### Export, Deployment, and Automation

- **Automated project validation with JSON reports**  
  Headless validation has been improved so that complete projects can be checked in automated builds and CI pipelines, with optional machine-readable JSON output.

  *Highlights:*
  - validate complete projects in headless builds
  - generate JSON reports with errors, warnings, resources, and line numbers
  - fail builds automatically when validation errors occur

- **Improved FORTE NG export**  
  FORTE NG export now handles additional modeling details more accurately, including adapter initial values and related composite FB configuration.

- **Deployment and export robustness**  
  Several fixes improve correctness and resilience in deployment and export workflows, especially around hierarchical models and untyped subapplications.


### Libraries, Devices, and Standard FBs

- **WAGO 750-636 support**  
  The WAGO library has been expanded with improved support for the 750-636 drive controller and its register communication workflows.

- **Standard FB improvements**  
  Several standard library function blocks were improved in behavior, configuration, and documentation.

- **Device communication profile filtering**  
  Device types can now restrict the communication profiles presented to users, so only supported profiles are shown.

### Everyday Usability and Robustness

- **Improved connection editing**  
  Connection handling has been improved for easier network cleanup and restructuring.

  Highlights:
  - more aggressive connection deletion
  - automatic merging of compatible connection paths during reconnect

- **Better search result context**  
  The Search References view now shows the relevant source line directly in the results, making it easier to understand hits before opening them.

- **Reload open editors from disk**  
  Open editors can now be reloaded after external file changes, without requiring users to close and reopen the editor manually.

- **Improved handling of broken or unresolved types**  
  If a type cannot be loaded, 4diac can now keep the project usable by representing the failure as an error library element. This improves error recovery and reduces the impact of malformed or unresolved resources.

- **Optional deletion explosion effect**  
  Deleting function blocks and connections can now trigger an optional visual explosion effect. It is a small but memorable usability touch that adds immediate visual feedback during editing.

### Additional Improvements and Fixes

In addition to the headline features above, 4diac IDE 3.3 includes many further improvements in connection handling, refactoring infrastructure, deployment data handling, search integration, type loading, editor robustness, and general maintenance. These changes help make 4diac IDE more stable, more predictable, and easier to use in larger real-world projects.


