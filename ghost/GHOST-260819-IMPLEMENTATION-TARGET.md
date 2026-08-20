# Gossie//Blackout — GHOST 260819 Implementation Target

**Status:** implementation-targeted / compliant-by-design work in progress.

This document is deliberately **not** a claim of “GHOST Verified,”
“GHOST Certified,” or “GHOST Complete.” Those claims require the applicable
GHOST 260819 controls to be verified and supporting evidence retained.

## Blackout security outcomes mapped to GHOST principles

| Blackout evidence ID | Required outcome | v0.5 implementation |
|---|---|---|
| BO-PREV-001 | Prevent casual/local bypass | Platform-native keyboard suppression; strict mode refuses to arm when unavailable |
| BO-PREV-002 | No reusable local software escape secret | Local unlock code/phrase removed |
| BO-AUTH-001 | Independent authorization | Early release requires a separately controlled Rescuer |
| BO-AUTH-002 | Explicit human authorization | Email GET only renders a confirmation page; state changes require POST button action |
| BO-LA-001 | Least authority | Relay can approve only a specific pending release/change request; no remote shell/control API |
| BO-TOKEN-001 | Single-use unpredictable capabilities | CSPRNG authorization tokens; only SHA-256 digests persisted |
| BO-TOKEN-002 | Bounded authorization | Rescue requests expire; consumed approvals cannot be reused |
| BO-BOOTSTRAP-001 | Minimize bootstrap-secret persistence | Enrollment token is discarded locally after relay acceptance |
| BO-FAIL-001 | Fail closed on network/service loss | Relay/email failure does not unlock Blackout |
| BO-FAIL-002 | Do not falsely claim enforcement | Client disarms/refuses strict mode when OS keyboard suppression cannot be established |
| BO-REC-001 | Owner recovery remains possible | Full reboot resets Blackout to START TIMER |
| BO-DET-001 | Detectable security state | Client exposes enforcement capability and verified-rescuer state |
| BO-AUD-001 | Tamper-evident operational evidence | Relay maintains a chained SHA-256 audit log |
| BO-PLAT-001 | Equivalent security outcome across platforms | Native Windows/macOS/X11 enforcement backends; unsupported sessions are rejected rather than downgraded silently |
| BO-CHANGE-001 | Rescuer replacement cannot become an escape path | Unarmed change verifies new rescuer; armed change requires current-rescuer approval and new-rescuer verification |

## Remaining verification work before any GHOST claim

- Threat model and abuse-case review against full canonical GHOST 260819.
- Dependency and supply-chain review.
- Secrets-at-rest review for client device identity and relay service credentials.
- TLS deployment configuration and certificate validation audit.
- Rate limiting / anti-abuse controls for public relay deployment.
- Formal relay authentication and account/enrollment lifecycle review.
- Platform-specific escape-route testing.
- Signed release pipeline and provenance.
- Update/rollback security.
- Log retention/privacy policy and deletion testing.
- Backup/recovery and relay database integrity testing.
- Independent test evidence retained for every applicable GHOST control.

The package therefore uses the phrase **GHOST 260819 implementation-targeted**
until those items are closed.
