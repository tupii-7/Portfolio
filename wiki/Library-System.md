# Digital Library Management System

## Overview

The library system manages books, members, catalog inventory, borrowing and
return workflows, authentication, and summary reporting through a Laravel
application backed by MySQL.

## Relational design

The schema separates catalog records from physical inventory and member
accounts. A loan transaction references both the member and the borrowed
inventory item, allowing the system to track checkout, due, and return dates
without losing historical activity when catalog details change.

## Transaction flow

1. Authenticate the staff user and validate the member and inventory item.
2. Confirm that the item is available before creating a loan.
3. Create the loan and mark the item as borrowed in one database transaction.
4. On return, record the return timestamp and restore item availability.
5. Expose aggregate counts and overdue records for dashboard reporting.

Atomic updates prevent a book from being issued twice when concurrent requests
arrive, while the loan history remains available for reporting.

## Reporting

Dashboard queries aggregate active loans, returned items, overdue items, member
counts, and inventory totals. Keeping these metrics derived from normalized
transaction tables avoids duplicating counters that can drift from the source
records.

