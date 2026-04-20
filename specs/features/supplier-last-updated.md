# Supplier `last_updated` Field Specification

**Parent Issue:** dbruun/octocat-supply-platform#1

## Overview

Add a `last_updated` timestamp field to the Supplier entity and expose it end-to-end:

1. **octocat-supply-api**: add schema migration + repository mapping
2. **octocat-supply-web**: show the field in supplier detail view

## Repository Scope

### octocat-supply-api
- Add a new migration that adds `last_updated` to `suppliers`
- Use an ISO 8601 timestamp value in API responses as `lastUpdated`
- Update supplier repository read/write mapping to include the field

### octocat-supply-web
- Extend supplier detail typing/model to include `lastUpdated`
- Render `lastUpdated` in the supplier detail page with a clear label
- Handle missing value gracefully (e.g., fallback text)

## Acceptance Criteria

- [ ] Supplier schema includes `last_updated`
- [ ] Supplier repository returns `lastUpdated` in API response payloads
- [ ] Supplier detail view displays `lastUpdated`
- [ ] No regressions in existing supplier flows
