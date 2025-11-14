---
author: ["Rickard Ahlstedt"]
title: "Array-54 - Split Keyboard Design"
date: "2025-05-21"
series: ["Array-54"]
description: "Custom split keyboard with 54 keys, powered by RP2040 Zero and KMK"
summary: "Designing and building a handwired split keyboard with a 3D printed case."
tags: ["split-keyboard", "ergonomics", "3d-printing"]
categories: ["project", "keyboard"]
draft: false
# weight: 1
cover:
    image: projects/Array54/images/splash.jpg
---

![](/projects/Array54/images/splash.jpg)

## Array-54 Overview

The Array-54 is a take on creating a productivity-focused split keyboard with focus on daily use for programming.

### Key Features

- Split design for better ergonomics.
- 3D printed case with multiple layout options.
- Powered by RP2040 MCU running CircuitPython, KMK firmware, and is fully configurable via POG.

### Design Philosophy

The Array-54 draws inspiration from the nordic landscape, with soft-edges derived from how tree-trunks adapt to their surrounding.  
This makes the keyboard feel more natural, whilst keeping a slim look.

![](/projects/Array54/images/money_shot.jpg)

The column-stagger was a natural decision, as pro-longed writing with row-staggered keyboards can lead to RSI due to the excessive movements done. This layout combats that with perfectly aligned rows and by staggering the columns the matrix follows the reach of each finger more naturally.  
Allowing each finger to control their respective column, limiting the rotation needed on the wrist and making it more comfortable for pro-longed sessions.

![](/projects/Array54/images/top_down.jpg)

The surfaces are clean to give a sense of clarity and minimalism, blending in with the rest of your deskarea, without standing out too much.

### Technical details

 - 54 Razer Green MX Switches
 - 2pc RP2040 Zero
 - Hardwired interconnect

## Lessons learned

*The following section is directly pulled from my Obsidian-vault, thus it may appear sloppy or unformatted*

### Proper column and row-wiring
With the cost of the overall thickness of the board, it will be worth adding 1-2mm in height of the volume inside of the case, so it can accommodate 16-18 awg solid wire for the matrix.
Alternatively use of low-profile switches might suffice if the requirement of a total height of 11mm is desired.

![](/projects/Array54/images/wiring_both.jpg)
*The blue-wire is thicker and makes the right half much more rigid*

### Support for hot plugging
I so wish I learnt this before the rev. 1, but TRRS is not hot-pluggable, and hot-plugging will result in shorting the controller.
For the rev. 2, USB-C will be used for communications between the two halves.

### Tight thumbcluster
Moving the 3-piece thumbcluster 1u to the inner-edge of each halves seems more comfortable and gives better flexibility for the thumb.

### No visible screws on the plate
As the title says, the screws that are m3 right now, gets in the way of the switches and interferes with the clamping force of nearby switches, so removing the screws from the plate is essential, and instead adding m2x4x3.5 heated inserts on the back of the plate and screwing in from the back will be better

### Better option for tenting and anti-slip
The tenting right now is not that good, need to brainstorm how to make it better.

### 2.7mm led-strip?
Just to mark down the idea of having a user-facing led-strip, so it can look nice when not in use and can be used as a "Do not Disturb"-indicator for office-environments

### Hot-swap sockets
Yup

### Turn the mcu upside down 
As well as holes in the bottom-case to allow easier access to RESET and BOOT-btns

### Integrated tenting-legs
Draw inspiration from Ergodox Ez, three legs that can be adjusted and fastened with a thumb-screw.

### Perhaps QMK would have been a better choice
KMK seems to be having some slowdowns when running tapdances and/or holdtaps on the primary layer.

## Conclussion

For a first build, this turned out quite good, feels good to type on, albeit some tenting is needed for prolonged sessions.  
As a revolution of this, I'm working on Array-58C, a dactyl/skeletyl-inspired split keyboard.