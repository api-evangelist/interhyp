---
name: Read a mortgage financing application
description: Retrieve an Interhyp financing application and its applicants, estates, households, financial standings and offer for review.
api: openapi/interhyp-submission-openapi.yml
operations:
- getFinancingApplicationById
- getApplicantsByFinancingApplicationId
- getApplicantById
- getEstatesByFinancingApplicationId
- getHouseholdsByFinancingApplicationId
- getFinanceStandingsByFinancingApplicationId
- getOfferByFinancingApplicationId
- getSubmissionsByFinancingApplicationId
---

# Read a mortgage financing application

Use the Interhyp Submission API to load a full financing application (Baufinanzierung) for review.

## Auth
Send both credentials on every request:
- `Api-Key: <partner api key>`
- `Authorization: Bearer <OAuth 2.0 JWT access token>`

Base URL: `https://api.interhyp.de/submission/v2` (production). Test: `https://api-test.interhyp.de/submission`.

## Steps
1. `getFinancingApplicationById` with the `financingApplicationId` to load the root aggregate.
2. `getApplicantsByFinancingApplicationId` to list applicants; call `getApplicantById` for each one's detail.
3. `getEstatesByFinancingApplicationId` and `getHouseholdsByFinancingApplicationId` for the property and household context.
4. `getFinanceStandingsByFinancingApplicationId` for income/assets/liabilities.
5. `getOfferByFinancingApplicationId` for the current financing offer.
6. `getSubmissionsByFinancingApplicationId` to see which loan-partner submissions exist for this application.

## Conventions
- Collections are cursor-paginated (`before`/`after` cursors); follow the cursor to page.
- Use the `Prefer: return=full` header or the `embed` query parameter to expand related resources inline; `return=essential` keeps payloads small.
- Errors are RFC 7807 problem objects (`application/json`) with a `traceId` — quote it to support (am@prohyp.de).
