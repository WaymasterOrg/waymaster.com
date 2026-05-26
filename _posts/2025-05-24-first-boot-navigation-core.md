---
layout: post
title: "First boot: Waymaster navigation core comes alive on the 560 SEC"
date: 2025-05-24
category: software
summary: "After three months of work, the core navigation engine booted for the first time inside the Mercedes. Rough, slow, but definitively real. Here's what happened."
---

## The Evening It Worked

There's a specific kind of anxiety that precedes a first boot. You've been writing code in the abstract for months — data structures, rendering logic, map tile parsers — and none of it is real until it runs on actual hardware, in an actual car, and doesn't immediately crash.

It didn't immediately crash.

The hardware was minimal: a Raspberry Pi 5 sitting on the passenger seat of the 560 SEC, connected to the OBD-II port via a USB adapter, driving a small HDMI display propped against the windscreen with a friction mount. No enclosure, no permanent wiring, a power bank taped to the glovebox lid. The kind of setup you'd be embarrassed to photograph.

## What Worked

**ASCII mode rendered correctly.** The display showed the navigation layout as designed — heading, speed, turn instruction and estimated arrival time, with the OBD data panel below showing oil temperature, coolant temperature and engine RPM. It looked, genuinely, like a period-correct instrument from another timeline.

**OBD data was live.** Via the K-line adapter, the M117 V8 was reporting real-time oil temperature (82°C after a short warm-up), coolant temperature and engine RPM. The data is stable and updating at roughly 2Hz, which is adequate for the gauges.

**Turn-by-turn basics functioned.** With a pre-loaded OSM map tile set, a simple test route generated and the first few turn instructions rendered correctly. The GPS fix was solid from a USB dongle sitting on the dashboard.

## What Didn't

**Font rendering needs work.** The VT323 display font I'm using for the ASCII mode is rendering slightly soft at the resolution I'm targeting. The fix is probably to bump the base resolution and scale down, but this needs investigation.

**Map data loading is far too slow.** Cold start to first tile display is around 8 seconds, which is unacceptable. The map engine is reading from SQLite on the SD card, and the bottleneck is almost certainly the card I/O. Solutions under consideration: move the map data to a USB SSD, implement better tile caching, or pre-render the most-used tile sets.

**GPS cold start.** First fix is taking 45–90 seconds from power-on, which means the system isn't ready when you want to leave. A GPS module with battery backup for hot-start would fix this — it's on the hardware list.

## Next Steps

The immediate priorities coming out of this test:

1. Resolve the map loading performance — USB SSD trial this week
2. Fix the font rendering at target resolution
3. Begin work on the vector display mode alongside ASCII
4. Permanent hardware mockup for the SEC (still on the passenger seat)

The platform is real. The software runs. Everything from here is refinement.
