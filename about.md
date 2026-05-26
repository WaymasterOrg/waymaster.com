---
layout: default
title: "About Waymaster"
description: "What Waymaster is, why it exists, and how it works — retro navigation and vehicle intelligence for classic cars."
permalink: /about/
---

<div class="category-banner">
  <div class="container">
    <h1>ABOUT</h1>
    <p>What Waymaster Is &bull; Why It Exists &bull; How It Works</p>
  </div>
</div>

<section class="section">
  <div class="container--narrow post-content">

## The Problem With Modern Sat-Nav in Classic Cars

A modern sat-nav in a classic car looks wrong. Not slightly wrong — fundamentally, categorically wrong. A glowing touchscreen in a 1989 Mercedes dashboard is a category error. The car was designed before such things existed, and the aesthetic coherence of the interior depends on nothing breaking that period.

The alternative — a phone mounted in a cradle on the windscreen — is pragmatic but graceless. It works. It doesn't belong.

Waymaster is the third option.

## What Waymaster Is

Waymaster is a navigation and vehicle intelligence system designed specifically for classic cars. It provides:

- **Route guidance** with turn-by-turn instructions, offline maps (OpenStreetMap data) and voice output
- **Vehicle monitoring** via OBD-II / CAN bus — oil temperature, coolant temperature, RPM, fuel level, fault codes
- **Two display modes** designed to be aesthetically appropriate to the vehicle

The software runs on inexpensive single-board computer hardware (currently targeting Raspberry Pi) and connects to a display panel mounted in or near the dashboard.

## The Two Display Modes

### ASCII Terminal Mode

The entire interface is rendered in character art — letters, numbers, box-drawing characters and block elements. No bitmaps, no icons, no graphics. The display looks like a terminal from 1982, because that's what a terminal from 1982 would have looked like if it had been designed as car instrumentation.

This mode works on any display, including low-resolution or vintage screens. It is the utilitarian choice — clear, readable, honest.

### Green Vector Mode

Vector line graphics rendered on a dark background in phosphor green. Roads are drawn as lines, not filled polygons. Instrument gauges are rendered as arcs and needles. The overall effect is a piece of hardware that could plausibly have existed in 1984 if someone very clever had been working at the intersection of arcade game technology and automotive instrumentation.

This mode requires a higher-resolution display (minimum 480p) and somewhat more processing power.

## The Technology

Underneath the period-correct surface, Waymaster uses contemporary technology:

- **OpenStreetMap** for map data, processed and packaged for offline use
- **GPSD** for GPS integration, supporting a wide range of USB and serial GPS modules
- **OBD-II via ELM327** or equivalent adapters for vehicle data
- **Home automation patterns** for system integration — MQTT messaging, event-driven architecture, modular sensor drivers

The home automation architecture is not incidental. Treating vehicle systems as sensors and actuators, with a message bus in between, makes the system extensible and testable in ways that traditional automotive software is not.

## The Test Vehicles

Development is happening on two real vehicles:

- A **1989 Mercedes-Benz 560 SEC** (W126) — primary test platform, currently being restored alongside the software development
- A **1984 Volkswagen T25 Westfalia** camper van — secondary platform, emphasising the touring and camping use cases

Both vehicles are documented in detail on this site. The mechanical and electrical work on the cars is as much a part of the project as the software.

## Current Status

Waymaster is in active development. The OBD-II monitoring layer is functional. The ASCII display mode is working on hardware. The navigation engine is in early development. The vector display mode is in design.

Follow progress on the [Dev Log](/devlog/) and [Blog](/blog/).

  </div>
</section>
