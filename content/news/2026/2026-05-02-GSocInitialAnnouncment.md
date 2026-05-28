---
title: "Welcoming Our Google Summer of Code 2026 Contributors!"
date: 2026-05-02T00:00:00-00:00
categories: ["GSoC"]
type: "newsitem"
description: |
  We are excited to share that the Eclipse 4diac Project has been selected to participate in Google Summer of Code 2026 and we are welcoming two student contributors who will be working with us over the summer!
fordiacTeamGreating: true
---


As Eclipse 4diac continues its journey toward industrial-grade maturity, these projects will help strengthen both the robustness of the IDE and the experience for its users.

### This Year’s Projects

- [**Strengthening Refactoring Quality through Automated Testing**](https://summerofcode.withgoogle.com/programs/2026/projects/yuMveNWN)  
    As code quality becomes increasingly critical, especially in industrial contexts, refactoring support in the 4diac IDE plays a key role. 
    This project focuses on improving the infrastructure for automated unit testing of our advanced refactoring features, helping ensure their correctness, reliability, and maintainability over time.
-  [**Enhancing the ECC Editor User Experience**](https://summerofcode.withgoogle.com/programs/2026/projects/2FIzvyaE)  
    While the 4diac IDE has seen significant usability and UX improvements in recent years, the ECC editor has not yet received the same level of attention. 
    This project will analyze the current state of the ECC editor and introduce targeted UI and UX improvements to make it more intuitive and efficient for users.

### Growing the Community

Google Summer of Code is a fantastic opportunity to bring new contributors into the Eclipse Foundation ecosystem and the Eclipse 4diac community. We are looking forward to working closely with our students, supporting them throughout the summer, and learning from their fresh perspectives.

A big thank you goes to our mentors, who are volunteering their time and expertise to guide these projects and help our contributors succeed.

Let’s give our students a warm welcome and support them on their journey. 
We’re excited to see what they will achieve!

---

## Project: Enhancing the ECC Editor User Experience

### Contributor: Vikash Kumar Sinha
**Organization:** Sant Longowal Institute of Engineering and Technology (SLIET), Punjab, India  
**Field of Study:** Computer Science (3rd Year)  
**Mentors:** Alois Zoitl and Eclipse 4diac Community
**Project size** Large

---

## About Me

I'm Vikash Kumar Sinha, a 3rd-year Computer Science student from Sant Longowal Institute of Engineering and Technology (SLIET), Punjab, India. I'm passionate about open-source development and building robust industrial automation tools. This summer, I'm thrilled to be contributing to Eclipse 4diac as part of Google Summer of Code 2026, focusing on enhancing the ECC (Event Chain Chart) editor's user experience.

My project aims to address key usability and visual quality issues in the ECC editor—making it more intuitive and efficient for users who rely on it for industrial automation workflows.

---

## Progress Summary

Over the past weeks, I've been working on improving the ECC editor's visual quality and usability. Here's what has been completed:

---

## Completed Work

### 1. Cubic Spline Transition Rendering

**PR:** [Fix ecc transition splines #2421](https://github.com/eclipse-4diac/4diac-ide/pull/2421)

Implemented smooth cubic spline curves for ECC transitions.

**What was improved:**
- Transitions now render as smooth curves instead of jagged straight lines
- Eliminated flickering during transition rendering
- Created ECCTransitionRouter for proper spline calculation

---

### 2. Connection Spacing and Anchor Positioning

**PR:** [Implement ECStateConnectionAnchor for better transition routing #2369](https://github.com/eclipse-4diac/4diac-ide/pull/2369)

Implemented intelligent anchor positioning for multiple transitions.

**What was improved:**
- Multiple transitions on the same state edge are now evenly spaced
- Prevents transitions from overlapping
- Automatically detects edge direction (TOP, BOTTOM, LEFT, RIGHT)

---

### 3. Edge Direction Architecture Refactor

**PR:** [Refactor edge direction #2430](https://github.com/eclipse-4diac/4diac-ide/pull/2430)

Refactored edge direction logic for better code quality and reusability.

---

### 4. State Offset and Coordinate System

**PRs:**
- [Fix zoom-aware coordinate translation in NewStateAction #2226](https://github.com/eclipse-4diac/4diac-ide/pull/2226)
- [Clean CreateECStateCommand to remove screen coordinate dependency #2189](https://github.com/eclipse-4diac/4diac-ide/pull/2189)
- [ECC Remove UI dependency from CreateTransitionCommand #2269](https://github.com/eclipse-4diac/4diac-ide/pull/2269)

Fixed state positioning issues:
- States now appear at the exact cursor position when created
- Improved zoom-aware coordinate handling
- Proper center-point calculation for state anchors

**Issue Addressed:** [New state created via CTRL+click appears offset from cursor position #2140](https://github.com/eclipse-4diac/4diac-ide/discussions/2140)

---

### 5. Documentation Updates

**PR:** [Update 4diac IDE import.png](https://github.com/eclipse-4diac/4diac-documentation/pull/94)

Updated documentation with improved screenshots.

---

## Key Improvements

Spline Rendering - Smooth, professional-looking transitions

Connection Spacing - Cleaner diagrams, no overlapping transitions

State Positioning - Accurate placement of states

Code Quality - Maintainable, well-documented code

---

## What's Next

I'm continuing to work on further ECC editor improvements based on community feedback and identified usability gaps.

---

## Community Engagement

I've been actively discussing potential future enhancements with the community:

- [Improving ECC Transition Routing #2228](https://github.com/eclipse-4diac/4diac-ide/discussions/2228)
- [Enhancing Transition Editing Experience #2285](https://github.com/eclipse-4diac/4diac-ide/discussions/2285)
- [Modernizing ECC Workflow #2169](https://github.com/eclipse-4diac/4diac-ide/discussions/2169)
