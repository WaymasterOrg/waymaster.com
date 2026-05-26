---
layout: post
title: "Mercedes 560 SEC: Diagnosing the idle hunt through CIS-E Jetronic"
date: 2025-05-10
category: mercedes
summary: "The SEC has been hunting at idle since acquisition. Three weeks of diagnosis through the Bosch CIS-E system — what the symptoms were, the process of elimination, and what finally fixed it."
---

## The Symptom

From the day I collected the car, it idled badly. Not catastrophically — the engine ran, it drove, it performed well under load — but at a standstill, the revs would hunt rhythmically between roughly 500 and 900 rpm. Every two or three seconds, up and down, like the engine was breathing too slowly.

This is a known characteristic of aging CIS-E systems, which is simultaneously reassuring (it's probably fixable) and dispiriting (it could be any one of six or seven things).

## The CIS-E System — A Brief Overview

The W126 560 SEC uses **Bosch CIS-E Jetronic** (also styled KE-Jetronic in some markets). It's a hybrid system — mechanical continuous injection at its core, with electronic correction layered on top. Fuel delivery is controlled by a mechanical fuel distributor, but the mixture is trimmed by an **electrohydraulic actuator (EHA)** that adjusts fuel pressure differentially based on signals from the ECU.

Key components relevant to idle quality:

- **Idle air control valve (IACV)** — a bypass valve that allows air around the throttle plate at idle
- **Auxiliary air valve** — a thermostatic device that increases idle speed from cold
- **Electrohydraulic actuator** — adjusts mixture richness in real time
- **Differential pressure regulator** — sets the base fuel pressure differential
- **Throttle position switch** — tells the ECU when the throttle is closed (idle state)
- **Oxygen sensor** — provides the closed-loop mixture feedback signal

Any of these can cause idle instability. The challenge is isolating which one.

## The Diagnosis Process

### Step 1: Vacuum leaks

The first and cheapest thing to check. A vacuum leak introduces unmetered air, which the ECU can't account for, causing rough idle. Systematic check with a smoke machine (and, less scientifically, a length of fuel hose used as a stethoscope) found nothing significant. A small weep at the brake servo hose was fixed and made no difference to the hunt.

### Step 2: Idle air control valve

The IACV is a rotary valve driven by a stepper motor. It was removed, cleaned with carburettor cleaner, and electrically tested — resistance within specification, mechanical movement free. Refitted, no change.

### Step 3: Auxiliary air valve

This is a bimetal-controlled valve that should be fully closed once the engine reaches operating temperature. At temperature, it was passing a small but measurable amount of air. A new unit was fitted. No change to the hunt, but the cold start behaviour improved noticeably.

### Step 4: Throttle position switch

The TPS tells the ECU the throttle is closed, which triggers the idle fuel map. Testing with a multimeter at the ECU connector showed the switch was intermittently failing to report closed position — the contacts were dirty. Cleaned and adjusted. The hunt reduced in frequency but didn't disappear.

### Step 5: Oxygen sensor

The lambda sensor was original and well beyond its service life. A new Bosch unit was fitted. The idle smoothed further, but the hunt persisted at low amplitude.

### Step 6: Electrohydraulic actuator

The EHA is the component that adjusts mixture in real time by modulating the fuel pressure differential across the fuel distributor. If it's hunting — making large corrections alternately rich and lean — the idle will hunt in sync.

Current measurement at the EHA connector at idle should be approximately 0mA on a well-adjusted engine (neither adding nor subtracting fuel from the base map). The car was showing ±8–12mA, oscillating — a clear sign the closed-loop system was chasing its tail.

Replacing the EHA is the nuclear option — it's expensive and not always the root cause. Before condemning it, I adjusted the CO potentiometer to centre the base mixture, which reduced the oscillation amplitude. But it didn't stop it.

The EHA was eventually replaced with a reconditioned unit. The hunt stopped.

## Result

Total cost of the repair: moderate, mostly absorbed by the auxiliary air valve, oxygen sensor, and EHA reconditioning. Total time: three weekends plus a lot of evenings reading W126 forum archives.

The SEC now idles at a rock-solid 700 rpm. It sounds exactly as it should — a muted, confident V8 with no drama.

## Notes for Anyone Doing This on a W126

Work through the list in cost order. Vacuum leaks and the throttle switch cost almost nothing to fix. The IACV and auxiliary air valve are inexpensive. The oxygen sensor is a known service item. The EHA is the last resort, not the first guess.

The Bosch CIS-E system is well-documented in the factory workshop manual (WIS) — if you're working on a W126, get a copy. The diagnostic procedures in section 07.3 are thorough and will save you hours.
