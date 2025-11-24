---
author: ["Rickard Ahlstedt"]
title: "02 - Constraints and caps"
date: "2025-08-01"
series: ["Node40"]
description: "Exploring the concept behind building a custom 40% split-keyboard"
summary: "Exploring the world of constraints and deciding on the caps."
tags: ["split-keyboard", "handwired", "hardware", "diy", "node40"]
categories: ["project", "split-keyboard", "build-log"]
draft: false
weight: 2
---

## Constraints

Designing a handwired board with a set height can be challenging, and I wanted to keep the MCU in the body, and not having an appendage like my previous Keyboard has.  
Thankfully, I (again) decided to use the RP2040 Zero, which has a small footprint and is not really that high.

![](/projects/node40/images/mcu_tight.PNG)

Don't let the angle give it away, take a look from another perspective.

![](/projects/node40/images/mcu_tight_front.PNG)

*Ehm*, yeah so it's tight, with roughly 0.5mm of clearance from the top of the USB-C port and the bottom of the plate.

But! It should fit, I will leave that to the test-print.

## Caps

I had a hard time deciding on the caps for this build, originally I was planning on using a [DSA-style caps](https://www.thingiverse.com/thing:2172302), so I printed a set to try it out.  
*Admittedly, I have tried some caps of this set before on my daily at home*

![](/projects/node40/images/dsa-test.jpg)

After evaluating the caps, listening to how they sound together with the board, I wanted to explore other options.  
I had previously seen [KLP Lamé](https://github.com/braindefender/KLP-Lame-Keycaps) caps, but at the time they didn't have 1.25 nor 1.5u caps so I put that to the side in favor of [CLP](https://github.com/vvhg1/clp-keycaps) which had the 1.5u cap I was looking for.

![](/projects/node40/images/clp-vs-dsa.jpg)
So I decided to give my resin-printer a spin, and printed two DSA-caps and a CLP-cap, and it was at this time I noticed that my resin becomes too brittle for the higher stems that the DSA has.  
And I generally liked the feeling of CLP better, so I decided to commit to printing them, and it took *a while*.

My resin-printer is not big, so at most I was able to fit 8 caps, per plate.  
One plate takes ~2hrs, and my keyboard has 40 keys.