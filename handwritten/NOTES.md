# Patch Notes

## Summary
- Fixed task search SQL so archived, search-term, and status filters are grouped correctly.
- Removed the artificial query-length delay from the API.
- Added validation for pagination values and invalid task statuses.
- Reset pagination when search/status filters change.
- Fixed frontend loading/error state handling and prevented stale requests from overwriting newer results.
- Kept the existing architecture and pagination approach unchanged.

## Not Changed
- Did not rewrite the API or frontend architecture.
- Did not add unrelated features.
- Did not change the H2 schema or seed data.

## Biggest Remaining Risk
Pagination still loads all matching tasks into memory before slicing the requested page. Production-scale data should use database-level pagination.

## AI / Tools
Used AI assistance to inspect the code, identify high-value bugs, and prepare focused fixes. Changes were reviewed against the existing application flow before applying them.
