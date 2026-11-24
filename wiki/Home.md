# Hi, I'm [Your Name]

**Software Engineer specializing in Data Systems & Analytics**

I build data-intensive applications with a focus on multi-source API integration,
reliable local/relational storage, and clean software architecture.

## Core Stack

- **Data & Storage:** SQLite, MySQL, API data enrichment, entity resolution, caching lifecycles
- **Software Engineering:** TypeScript, React Native (Expo), PHP (Laravel 12), JavaScript
- **Data Sources Integrated:** U.S. FDA (openFDA), NIH DailyMed & RxNorm, Open-Meteo

---

## Featured Projects

### 1. MedSearch — Multi-Source Drug Label & Safety Analytics App

> **Focus:** Multi-API orchestration, deterministic entity matching, local SQLite caching

Cross-platform mobile application (Android, iOS, Web) that aggregates drug
labeling, recall trackers, and adverse-event analytics from the U.S. FDA,
enriched with verified packaging imagery.

- **Data Engineering Highlight:** A four-tier deterministic matching pipeline reconciles `openFDA`, `RxNorm` (RxCUI normalization), and DailyMed SPL records using exact NDC and active-ingredient rules to eliminate false-positive media matches.
- **Tech:** TypeScript, React Native (Expo SDK 58), Expo SQLite, openFDA API, DailyMed API, RxNorm REST API.
- **Links:** [Repository](https://github.com/tupii-7/med-search-app) · [Architecture & Data Flow](MedSearch-Case-Study)

### 2. [App Name] — Offline-First Weather & Air Quality Tracker

> **Focus:** Cache invalidation strategy, data freshness lineage, offline persistence

Mobile weather and AQI client backed by Open-Meteo geocoding and forecast
endpoints with resilient local storage.

- **Data Engineering Highlight:** A three-state local SQLite caching policy supports live fetches, fresh cache hits, and stale-while-offline fallback, with automated pruning for records older than seven days and explicit UI data-source indicators.
- **Tech:** TypeScript, React Native (Expo SDK 57), Expo SQLite, AsyncStorage, Open-Meteo APIs.
- **Links:** [Repository](https://github.com/your-username/your-weather-repo) · [Caching Architecture](Weather-Cache-Case-Study)

### 3. Digital Library Management System

> **Focus:** Relational database design, transactional workflows, reporting

Web-based library operations system managing catalog inventory, member records,
borrowing/return transactions, and summary reporting.

- **Engineering Highlight:** Structured relational MySQL schema supporting authenticated CRUD operations, loan lifecycle tracking, and aggregated dashboard metrics.
- **Tech:** Laravel 12, PHP, MySQL, Bootstrap 5, JavaScript.
- **Links:** [Repository](https://github.com/your-username/your-library-repo) · [Database & Features](Library-System)

---

## Upcoming Data Projects

*(Reserved for dedicated ETL pipelines, analytics dashboards, or machine learning studies.)*

