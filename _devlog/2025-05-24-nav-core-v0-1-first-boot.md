---
layout: devlog
title: "Nav core v0.1 boots on SEC hardware"
date: 2025-05-24
version: "v0.1"
summary: "First successful hardware boot of the navigation core. ASCII mode rendering correctly, OBD-II data live."
---

## What happened

First boot on actual vehicle hardware. Pi 5 on passenger seat, USB OBD-II adapter, HDMI display propped on dash.

- ASCII mode rendered correctly at target resolution
- OBD-II bridge returning stable data: oil temp, coolant, RPM
- GPS fix acquired in ~55 seconds (cold start)
- Turn-by-turn instructions generating from pre-loaded OSM tiles

## Issues logged

- Map tile load time: ~8 seconds cold — unacceptable, investigating USB SSD
- Font softness at current resolution — needs work
- GPS cold start too slow — battery-backup module on order

## Next

Map performance is the priority. USB SSD trial scheduled for next session.
