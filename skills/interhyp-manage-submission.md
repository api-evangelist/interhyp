---
name: Manage a mortgage submission
description: Inspect an Interhyp submission, run a pre-submission check, and apply state changes via the asynchronous command pattern.
api: openapi/interhyp-submission-openapi.yml
operations:
- getPreSubmissionChecksByIntentIdAndLoanPartnerId
- modifyPreSubmissionCheck
- getSubmissions
- getSubmissionById
- getSubmissionStatusById
- getLogbookBySubmissionId
- modifySubmission
- getCommandsById
---

# Manage a mortgage submission

Use the Interhyp Submission API to check eligibility, review a submission, and change its state safely.

## Auth
- `Api-Key: <partner api key>`
- `Authorization: Bearer <OAuth 2.0 JWT access token>`

Base URL: `https://api.interhyp.de/submission/v2`.

## Steps
1. Run a pre-flight check with `getPreSubmissionChecksByIntentIdAndLoanPartnerId` (intent id + loan partner id); answer/modify it with `modifyPreSubmissionCheck`.
2. List submissions with `getSubmissions` or load one with `getSubmissionById`.
3. Read `getSubmissionStatusById` and `getLogbookBySubmissionId` for current state and history.
4. To change state, POST a command with `modifySubmission`. This returns a `commandId` — mutations are asynchronous.
5. Poll `getCommandsById` with that `commandId` until the command completes.

## Idempotency & errors
- State changes go through the command resource, not direct writes; re-reading a command is safe and repeatable — this is the provider's idempotency contract.
- Business-rule rejections come back as `CommandError` codes (see `errors/interhyp-error-codes.yml`), e.g. `FINAL_STATE` (submission is immutable), `SBM_STATUS_CHANGE_DENIED` (illegal transition), `PRE_INQUIRY_ALREADY_SUBMITTED`. Treat `errorCode` as an extensible enum — tolerate unknown values.
- Transport errors are RFC 7807 problems with a `traceId`.
