# Lease Mileage Calculator

A simple, offline-capable web app to calculate your current mileage cap for a vehicle lease based on start date, term, and annual allowance. Prorates linearly by days elapsed. Built with vanilla HTML/CSS/JS—no backend needed.

Live demo: [https://allpurposeben.github.io/lease-calc/](https://allpurposeben.github.io/lease-calc/).

## Features
- **Web UI**: Mobile-friendly form with autofill via URL params.
- **API Mode**: Fetch JSON via curl/scripts (e.g., for automation).
- **Offline**: Works in Safari (add to Home Screen for app feel).
- **Accurate Proration**: Uses exact days (handles leap years via JS Date).

## Quick Start
1. Open the live URL in Safari/Chrome.
2. Enter: Start date, term (months), annual miles.
3. Tap **Calculate** → Gets current cap (e.g., as of Dec 05, 2025: ~3,717 miles for 36-mo/12k annual from Jan 1).
4. For iOS: Share > Add to Home Screen.

## URL Parameters (Autofill & API)
Append `?key=value` to the URL for pre-fills or programmatic use. All params optional unless noted.

| Param | Type | Description | Example |
|-------|------|-------------|---------|
| `startDate` | YYYY-MM-DD | Lease start (required for calc) | `2025-01-01` |
| `termMonths` | Integer | Lease term in months (required) | `36` |
| `annualMiles` | Number | Annual allowance (required) | `12000` |
| `format` | String | Output: `html` (default) or `json` (API mode) | `json` |

- **Autofill Example**: `?startDate=2025-01-01&termMonths=36&annualMiles=12000` → Fills form + auto-calcs in UI.
- **Partial**: Just `?termMonths=36` → Fills that field only.
- **JSON API Example** (requires all core params):  
  `?startDate=2025-01-01&termMonths=36&annualMiles=12000&format=json`  
  Curl:  
