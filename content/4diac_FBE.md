---
title: "4diac FBE"
seo_title: "4diac FBE"
headline: > 
  What is <span class="white">4diac™ FBE</span>?
tagline: >
  <br><span class="white">4diac™ FBE</span> is a versatile and easy to use <br><span class="white">build environment</span> for 4diac FORTE.
description: "This is the 4diac FBE page of Eclipse 4diac."
date: 2024-02-15T10:00:00-04:00
hide_breadcrumb: true
hide_page_title: true
page_css_file: /4diac/css/forte.css
#hide_sidebar: false
#sidebar_layout: "sidebar_block" # default
---

{{< br >}}
4diac FBE is a build environment for building [4diac FORTE](../4diac_forte/). Part of its workflow is code generation and re-compilation of 4diac FORTE. 
4diac FBE provides the means to do this with as little effort as possible.

Furthermore, you can manage multiple builds for multiple target platforms. 
Currently it works on Linux and Windows hosts. 
Supported targets are Linux (x86, ARM, MIPS, …) and Windows as well; macOS should be easy to add, others might need some more work.

Cross-compilation is built-in: you can generate binaries for all supported platforms on a single build host.

The 4diac FORTE executable built by this build environment will have all optional features enabled: OPC-UA, MQTT, Modbus, and with an extra setup step also openPOWERLINK. It does not enable platform-specific features like OPC (no -UA) by default, but different builds can have different target-specific configuration options.

All resulting executables will be statically linked, so there is nothing to deploy beyond the actual executable file, and it will not depend on any system packages/features. Exception: Windows targets will depend on system DLLs that probably come with Windows since XP, maybe even earlier. Full-featured executable size is around 4MB, this varies slightly across targets.

For more information and documentation on how to use it visit the [4diac FBE Github Repository](https://github.com/eclipse-4diac/4diac-fbe).

