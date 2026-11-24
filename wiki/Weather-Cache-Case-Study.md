# Weather Cache Case Study

## Overview

This offline-first weather and air-quality client uses Open-Meteo geocoding and
forecast endpoints, with SQLite persistence for reliable access when network
connectivity is unavailable.

## Cache states

- **Live fetch:** Request fresh data when the network is available and persist
  the response with its retrieval timestamp.
- **Fresh cache hit:** Reuse a still-fresh local record without an unnecessary
  network request.
- **Stale-while-offline fallback:** Display the most recent local record when a
  live request is unavailable, clearly indicating its data source and age.

Records older than seven days are pruned automatically to keep the local store
bounded. Freshness metadata is kept alongside the forecast so the interface can
explain whether the displayed result came from the network or local storage.

## Data lineage

Each cached result retains its location, request parameters, retrieval time, and
source state. This makes refresh behavior observable and prevents a stale
forecast from appearing indistinguishable from a live response.

