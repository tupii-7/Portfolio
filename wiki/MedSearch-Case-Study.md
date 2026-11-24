# MedSearch Case Study

## Overview

MedSearch combines U.S. FDA labeling, recall, and adverse-event data with
verified drug packaging imagery. The application uses local SQLite storage to
keep normalized results available across mobile and web sessions.

## Matching and enrichment flow

1. Normalize the user query and resolve candidate products through openFDA.
2. Prefer exact National Drug Code (NDC) matches when identifying a product.
3. Normalize active ingredients and use them as a deterministic fallback.
4. Resolve RxNorm identifiers (RxCUI) for canonical drug terminology.
5. Match DailyMed SPL records and accept packaging media only when product identity
   remains consistent.

The ordered pipeline favors precision over broad but ambiguous matches. Each
fallback is explicit so a missing identifier does not silently become an
unrelated media result.

## Local data model

The SQLite layer stores normalized product metadata, source identifiers, cached
responses, and timestamps. Source identifiers are retained separately so records
can be refreshed or traced back to the originating API without duplicating
provider-specific payloads throughout the application.

## API orchestration

The client treats each provider as an independent enrichment stage. Partial
provider failures preserve already-resolved data and are surfaced to the UI
instead of producing a success-shaped result with unverified imagery.

