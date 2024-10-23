---
title: "4diac FORTE"
seo_title: "4diac FORTE"
headline: > 
  What is <span class="white">4diac™ FORTE</span>?
tagline: >
  <br><span class="white">4diac™ FORTE is a </span>real-time capable <br>IEC 61499<span class="white"> Run-Time Environmen</span>.
description: "This is the 4diac FORTE page of Eclipse 4diac."
date: 2024-02-15T10:00:00-04:00
hide_breadcrumb: true
hide_page_title: true
page_css_file: /4diac/css/forte.css
#hide_sidebar: false
#sidebar_layout: "sidebar_block" # default
---

{{< br >}}
The 4diac FORTE is a small portable implementation of an IEC 61499 runtime environment targeting small embedded control devices (16/32 Bit), implemented in C++. It supports online-reconfiguration of its applications and the real-time capable execution of all function block types provided by the IEC 61499 standard.

4diac FORTE supports all IEC 61131-3 edition 2 elementary data-types, structures, and arrays. It provides a scalable architecture which allows 4diac FORTE to adapt to the needs of your application. Applications can consist of any IEC 61499 element as basic function blocks (BFBs), composite function blocks (CFBs), service interface function blocks (SIFBs), adapters and subapplications. For connections between function blocks 4diac FORTE uses automatic and save castings (e.g., INT -> REAL). 4diac FORTE provides a flexible communication infrastructure via so called communication layers.

## Supported Operating Systems
- [eCos](http://ecos.sourceware.org/)
- [freeRTOS](https://kb.hilscher.com/display/RCX/rcX)
- [NET+OS 7](http://www.digi.com/products/wireless-wired-embedded-solutions/software-microprocessors-accessories/software/netos)
- [PikeOS](https://www.sysgo.com/products/pikeos-hypervisor/)
- Posix: Cygwin, Linux (i386, PPC, ARM)
- [rcX](https://kb.hilscher.com/display/RCX/rcX)
- [Eclipse ThreadX](https://threadx.io/)
- [VxWorks](http://www.windriver.com/products/vxworks/)
- Windows

## Supported communication layers
- Ethernet (TCP/UDP)
- Ethernet PowerLink using [openPOWERLINK V1.8.0](http://sourceforge.net/projects/openpowerlink/)
- FBDK ASN.1 encoding
- Modbus TCP client using [libmodbus](http://libmodbus.org/)
- MQTT using [Eclipse Paho](http://www.eclipse.org/paho/)
- OPC UA using [open62541](https://github.com/open62541/open62541)
- OPC DA client using [OPC Client library release 0.4](http://sourceforge.net/projects/opcclient/)
- RS232


## Supported Boards

- [BeagleBone Black](http://beagleboard.org/black)
- [Digi Connect ME (ARM7)](http://www.digi.com/products/embedded-systems)
- [emBRICK](http://www.embrick.de/) for Raspberry PI and BeagleBone Black
- [Lego Mindstorms EV3 (ARM7)](http://mindstorms.lego.com/en-us/Default.aspx)
- [NXH 51-ETM](http://www.hilscher.com/)
- [Raspberry PI](http://www.raspberrypi.org/)


## Supported Programmable Logic Controllers (PLCs)
- [Bachmann electronic M1 PLC](http://www.bachmann.info/en/products/controller-system/)
- [icom MR-router series](https://www.insys-icom.de/icom-smartbox/container) 
- [MicroControl uMIC.200](http://www.microcontrol.net/en/products/control-systems/umic200/)
- [Phoenix Contact PLCnext](https://www.phoenixcontact.com/en-pc/products/plcnext-technology)
- [Raspberry-SPS](http://raspberry-sps.de/)
- [Revolution Pi](https://revolutionpi.com)
- [WAGO PFC200](http://global.wago.com/en/products/new-items/overview/pfc200-1.jsp)


