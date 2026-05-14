---
title: "Reference-grade Audio at Home: Monitor speakers"
description: "Speakers project"
publishDate: "10 Nov 2022"
tags: ["audio", "pcb", "electronics"]
---

Similarly to the case of the [[reference amplifier]](https://jzsfv.github.io/posts/projects/refaudio_amp), I set out to complete this project to occupy myself productively during the pandemic. Although I had been building audio equipment of varying complexity for about 10 years at that time, none of my previous works were technically as challenging. The loudspeaker system presented here is completely my original design.

## Design
The concept was clear: a pair of two-way midfield studio monitors with peak SPL @1m in line with comparable products on the market (>110 dB SPL unweighted). As such, accurate on-axis response (+/- 1.5 dB in the 40-22000 Hz frequency range) took priority over wide directivity and efficiency.

A SEAS P21REX woofer and a 25TAF/G tweeter were selected as the drivers for availability and superior quality control. This allowed the cabinet simulations based on the supplied TS parameters and responses to be realistic up to only needing fine-tuning later at the build stage. A fourth-order ported alignment was chosen for extended accurate bass response.

The internal aspect ratio of the enclosure is typical at 1/1.62/2.63 to avoid strong internal acoustic modes but keep the driver as close to a wall (behind) as possible. Stiffener shelves interconnected by stiffener bars were added at division points observing non-integer ratios along the height to break up baffles into smaller 'effective resonators'. As such, panel resonance frequencies spread over a wider spectrum that is high enough to be efficiently damped.

A double front baffle (for extra mass) holds the flush-mounted drivers. Chamfered front edges and woofer cut-outs help reduce diffraction.

![Speaker CAD model](./spk_pics/model.jpg)

## Implementation
Material choices were conservative: birch plywood sheets with high stiffness (thus higher resonance frequencies) held together by PVA glue. The double front baffle implements a semi-CLD structure with a thick layer of glue in between.

Drivers were mounted using EPDF gaskets to minimise leakage. A dampener rubber sheet placed between the magnet of the woofer and the middle shelf isolates the non-moving parts of the woofer from the enclosure in order to reduce vibration transmission.

Measurements were taken of the woofers' impedance curves in the bare enclosure to determine the sufficient amount of acoustic damping, which was realised by cutting up an old woollen rug and using it as lining. Similar measurements were used for tuning adjustable-length plastic tubes to achieve the desired port resonance frequency of 33 Hz.

The drivers were wired directly to the crossover placed on the back of the enclosure. Apart from ensuring airtightness, this provides quick access for modifications/repurposing, e.g., bi-amping conversion.

![Speaker building procedure](./spk_pics/build.jpg)

## Crossover
Exhaustive simulations of the crossover were run using impedance and frequency response data from measurements of the drivers in the finished enclosure. The picture below shows the optimised schematics, implementable using off-the-shelf resistors and capacitors. Air-core inductors were hand-wound to accommodate custom values with high precision.

![Crossover calculation](./spk_pics/crossover_calc.png)

Please note that the measurement environment was not acoustically ideal. Therefore, the displayed graphs include room modes at low frequencies, which are negligible for crossover calculations. Additionally, the design assumes a 4th-order LR high-pass filter with a corner point at 28 Hz in the signal path. This ensures the woofer excursion does not exceed its mechanical limits at frequencies inaudible to humans.

Taking the current requirements of the application into account, the PCBs include multi-layer ground and signal planes for both drivers. They are populated with high-quality industrial (non-boutique) polypropylene film capacitors and silicone-coated wire-wound power resistors, and feature footprints for some additional components. With the benefit of hindsight, spade connectors to the amplifier do not seem to be a practical choice, however rarely they are used.

![Crossover PCB](./spk_pics/crossover_pcb.jpg)
![Crossover](./spk_pics/crossover.jpg)

## Finished product
One of the finished speaker pair is shown below. Potential improvements include the felt lining of the front baffles, and crossover modifications to steer the axis along which the drivers' outputs sum flat.

![Finished product](./spk_pics/speaker.jpg)
