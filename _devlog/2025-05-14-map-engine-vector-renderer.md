---
layout: devlog
title: "Map engine: switched to custom vector renderer"
date: 2025-05-14
version: "v0.1"
summary: "Ditched the OSM tile renderer in favour of a custom vector approach. 40% faster load, better visual control."
---

## Change

Replaced OSM raster tile pipeline with a custom vector renderer reading directly from a PBF extract.

Reasons:
- Raster tiles were too visually busy — hard to apply the phosphor-green aesthetic cleanly
- Load times were dominated by PNG decode, not I/O
- Vector gives full control over line weights, colours, label rendering

## Results

- Cold load time: down from ~8s to ~4.8s (still not good enough but better)
- Visual quality: significantly improved — map now looks period-correct
- Memory: vector approach uses ~30% less RAM at equivalent detail level

## Still to do

- Further reduce cold start time (target: under 2 seconds)
- Implement tile pre-caching for frequent routes
- Label rendering at different zoom levels needs refinement
