---
title: "4diac IDE"
headline: > 
  What is <span class="white">4diac™ IDE</span>?
tagline: >
  <br><span class="white">4diac™ IDE is an </span>IEC 61499 <br><span class="white">Compliant Development Environment</span>.
seo_title: "4diac IDE"
description: "4diac IDE is an integrated development environment for developing distributed control applications according to the models of IEC 61499. For modelled applications and application components (IEC 61499 function blocks) code is gneerated and they can be downaloded to distributed field devices according."
date: 2024-02-15T10:00:00-04:00
hide_breadcrumb: true
hide_page_title: true
page_css_file: /4diac/css/4diacIDE.css
#hide_sidebar: false
#sidebar_layout: "sidebar_block" # default
---

{{< br >}}
{{< image src="/4diac/img/ide.png" alt="4diac IDE" width="100%" display="block" margin-left="auto" margin-right="auto" >}}
{{< br >}}

The 4diac IDE is based on the [Eclipse Platform](https://projects.eclipse.org/projects/eclipse.platform), which allows an easy integration of other plug-ins to the 4diac IDE providing new or extended functionality. 
IEC 61499-based systems follow an application centric design, which means that the application of the overall system is created at first.
Each application is created by interconnecting the desired function blocks (FB) in terms of a function block network (FBN). 
As soon as the hardware structure is known it can be added to a project's system configuration and the already existing application can be distributed onto the available devices.

The IDE provides the following features:

- **System Explorer:**
    manage IEC 61499 projects which consist of applications, a system configuration and a project specific type library
- **Application Editor:**
    modelling of IEC 61499 function block networks utilizing the type library's elements
- **Hardware Editor:**
    specification and parameterization of automation hardware by modelling of IEC 61499 devices
- **Type Editors:**
    creation of Basic FBs (BFB), Composite FBs (CFB), Service Interface FBs (SIFB), and Adapters
- **Distribution Editor:**
    mapping of FBNs or single FBs to the specified resources
- **Deployment:**
    selective download of applications to their corresponding resources
- **Monitoring and Debugging Functionalities:**
    watch and force the values of interface elements as well as trigger events
- **Testing Functionalities:**
    test and debug a single FB on its behavior by manually setting data values and debugging through the algorithms using break-points and step through the code.
    
