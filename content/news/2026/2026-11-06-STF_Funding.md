---
title: "Sovereign Tech Fund Invests in Eclipse 4diac"
date: 2026-11-06T00:00:00-00:00
categories: ["announcements", "Eclipse 4diac Project News"]
type: "newsitem"
description: |
  We have big news: the [Sovereign Tech Fund](https://www.sovereign.tech/programs/fund) is investing in Eclipse 4diac! From October 2026 through November 2027, we will tackle a coordinated development effort across the runtime, engineering tools, libraries, and documentation.
fordiacTeamGreating: false
---

We are thrilled about this opportunity. Our community has built a substantial foundation over many years. Now we can bring several important developments together and address obstacles to broader industrial adoption. Our ambition is a clear path from the first installation to a working, maintainable automation application, with more possibilities for everyone building with Eclipse 4diac.

### 4diac FORTE: strengthening the industrial foundation

Reliable communication and predictable runtime behavior are essential when moving from an engineering project to a real machine. Our work on 4diac FORTE will strengthen that foundation in three areas:

- **EtherCAT integration:** Complete and stabilize the existing integration of the EtherLab EtherCAT Master, supported by benchmarks for cycle timing, synchronization, and determinism. We will also implement and test recovery from bus interruptions.
- **OPC UA performance:** Investigate bottlenecks and optimize memory allocation and data paths. Automated benchmarks will compare memory consumption and throughput against the starting point.
- **Dynamic type loading:** Rework the mechanisms for transferring and executing new function block types, including the corresponding generation and deployment support in 4diac IDE.

Together, these improvements should make industrial integration more practical and allow applications to evolve without rebuilding the entire runtime whenever a new function block type is introduced.

### 4diac IDE: making engineering easier

Understanding an application, finding a problem, and making a controlled change are everyday engineering tasks. Our work on **4diac IDE** will support these tasks in three areas:

- **Engineering workflows:** Improve usability, responsiveness, and state handling to make everyday development more efficient.
- **Debugging and monitoring:** Extend debugging, monitoring, and visualization workflows to help you see what your application is doing and move more directly from an observation to its cause.
- **Architecture and testability:** Improve the separation between user-interface and service logic in selected parts of the tooling. Reproducible build processes and additional automated tests will make changes easier to verify.

Together, these improvements should make engineering tasks more straightforward and help preserve progress as the project develops.

### Reusable libraries: building on proven solutions

A useful building block should be easy to bring into another application and remain manageable when it changes. Our work on the **library infrastructure** will support this in three areas:

- **Independent library releases:** Establish a dedicated **4diac LIB repository** so that standard function block libraries can be maintained, versioned, and released independently of 4diac IDE.
- **Package distribution:** Add GitHub as a library repository provider, giving contributors a clearer path to publishing packages that others can build on.
- **Controlled updates and migration:** Improve dependency handling and traceability between package versions. Extended refactoring and migration support will be backed by automated validation and regression tests.

Together, these improvements should make it easier to reuse proven solutions while retaining control over dependencies and updates, and provide a clearer path for contributors to maintain shared libraries.

### From first steps to industrial applications

The capabilities need to come together in an example you can explore yourself. An industrial reference project will demonstrate a realistic control task and reusable building-block patterns.
A test setup with simulated inputs and outputs will allow the reference application to run without physical machinery. Revised documentation and step-by-step tutorials will connect installation, libraries, runtime, and engineering workflows into an end-to-end getting-started path.

### Who is working on this project

The funded work is carried out by the following organizations, working openly in the Eclipse 4diac community:

- **[MSR Software GmbH](https://www.msr-software.de/)**
- **[Osoft e.U.](https://www.osoft.at/)**
- **[LIT Cyber-Physical Systems Lab](https://www.jku.at/lit-cyber-physical-systems-lab/)**

Individual contributors from these organizations collaborate through the public Eclipse 4diac repositories and community channels.

### Let’s build the next step together

The results will be developed publicly in the Eclipse 4diac repositories, where they can be reviewed, used, and improved by the community.
Thank you to everyone whose contributions have brought Eclipse 4diac this far, and to the Sovereign Tech Fund for investing in its continued development. Bring your requirements, test cases, practical experience, and ideas. They will help us turn this opportunity into improvements that matter.
We have a lot ahead of us. We want this work to expand what you can achieve with Eclipse 4diac. We cannot wait to build it together!

*Moritz Pflaum, MSR Software GmbH*
