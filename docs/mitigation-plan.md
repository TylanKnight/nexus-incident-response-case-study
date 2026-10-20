# Proposed risk mitigation plan

All actions below are proposed. Day counts begin at hypothetical plan approval. They are not completed work or commitments by a real organization. Active exploitation would require immediate incident response rather than waiting for a scheduled milestone.

| Target | Risk addressed | Proposed owner | Proposed action | Verification required before closure |
|---|---|---|---|---|
| Day 30 | Misuse of employee or privileged credentials | Identity team | Require phishing-resistant MFA for remote and privileged access | Documented coverage and attempted unauthorized-access checks |
| Day 30 | Exploitation of exposed software | System owners | Prioritize patches or compensating restrictions | Version/configuration evidence and a relevant retest |
| Day 60 | Unnecessary movement between environments | Network engineers | Restrict development-to-production routes and vendor paths | Allowed and blocked connection tests plus service checks |
| Day 60 | Exposure of build credentials and signing keys | Release engineering | Remove shared secrets and limit key access | Permission review and unauthorized-access test evidence |
| Day 60 | Record-level access failures and resource exhaustion | Application owners | Test authorization and request quotas | Negative authorization and rate-limit tests with legitimate-use checks |
| Day 90 | Unrecoverable service or data loss | Operations | Demonstrate restoration from protected isolated backups | Restored-data integrity and service validation results |
| Day 90 | Upstream network saturation | Network operations and provider | Exercise upstream DDoS filtering | Recorded exercise observations and service recovery checks |
| Day 90 | Inadequate visibility | Security analysts | Validate endpoint, centralized-log and IDS/IPS coverage | Usable telemetry and expected alert generation |
| Day 90 | Reporting and third-party coordination gaps | Security, HR and procurement | Training and confirmed incident contacts | Training records and verified contact/evidence-sharing procedures |

## Change and closure records

For each action, record the affected asset, threat, vulnerability, owner, proposed effort/budget, dependencies, due date, current and residual risk, status, rollback plan and evidence of verification. The acceptance wording in this portfolio table is a condensed adaptation of the report's closure requirements.

Back up configurations, test in isolation, obtain change approval, introduce a limited rollout and verify service health before expansion. Failed verification reopens the task. Exceptions need an accountable decision, compensating controls and an expiry date.

Proposed review measures include overdue critical fixes, privileged-account authentication coverage, restore-test results, telemetry coverage and repeat incidents. No baseline or achieved improvement is available.

Source: original report pp. 20 and 22–23.
