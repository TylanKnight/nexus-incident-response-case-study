# Synthetic incident analysis report

**Case:** NEXUS-LAB-001  
**Date:** October 20, 2026  
**Status:** Guided analysis documented; transfer of the export remains unconfirmed.  
**Participation:** Tylan Knight completed an interactive discussion with assistant coaching. The assistant edited the accepted summary, mapped findings to records and generated the UTC timeline. This report does not represent an independent assessment or production incident response.

## Case summary

The logs show that the support.demo session viewed 12 records and created an export containing 1,200 records, followed by allowed outbound traffic from the same server. A separate connection was blocked, but the available evidence does not confirm whether the export was transmitted or who operated the account. I would preserve the relevant evidence, verify whether any external transfer was authorized, and request endpoint and transfer records to determine what was sent.

This is the summary reviewed and accepted during the guided discussion. Its supporting records are P01, P02, N01 and N02, with session context from A03/A04. The phrase “export containing 1,200 records” reflects the application event’s reported count; the actual exported file was not provided or inspected.

## Scope and evidence

The exercise contains 13 assistant-generated fictional events and a fictional context file. It concerns support.demo, VPN session S-104 and the support-app host. No real accounts, victims, collected telemetry or production systems were examined.

| Evidence | Location | What it supports |
|---|---|---|
| E01 | [events.jsonl](data/events.jsonl) | Recorded synthetic identity, VPN, application, network, IPS and scheduler events |
| E02 | [context.json](data/context.json) | Asset mapping, approved backup context, clock assumptions and deliberate gaps |
| Integrity reference | [SHA256SUMS.txt](SHA256SUMS.txt) | SHA-256 values recorded after generation; checked again when preparing this report |
| Derived timeline | [timeline.md](timeline.md) | All 13 events with original timestamps, normalized UTC times and interpretation |

The assistant rechecked both input hashes against the existing manifest without changing either file. Hash agreement confirms consistency with that generated-file baseline; it does not authenticate real-world events. No actual copy of export-017.json, endpoint image or network payload exists in the supplied exercise evidence.

## Findings

### F01 — Successful authentication does not establish compromise

A01 and A02 record two failed sign-ins, followed by success in A03. A04 assigns session S-104 the VPN address 192.0.2.44. This sequence supports investigation but could also reflect a legitimate user correcting a password. A03 records that MFA was not required; it does not establish who used the account.

### F02 — Application access and export creation are recorded

P01 records 12 viewed records. P02 records creation of export-017.json with a reported 1,200 records and 480,000 bytes. Both events identify support.demo and S-104 on support-app. The export count and view count describe separate operations; the evidence does not show their record-level overlap.

### F03 — N01 is allowed outbound traffic with unknown content

N01 records 510,000 outbound bytes from support-app to 203.0.113.77 on port 443 at 16:07 UTC, one minute after P02. Shared host and close timing are relevant clues. They do not connect a particular file to the transfer. Process identity is missing and content is not visible. Neither byte-count similarity nor the destination’s absence from the provided approved register proves theft or maliciousness. Whether any or all of the export was transmitted remains unknown.

### F04 — N02 blocks a separate connection

N02 records traffic from 198.51.100.23 to 192.0.2.80 at 16:08 UTC as blocked. N01 has different endpoints and was recorded allowed. The N02 action does not undo N01 or establish that N01 was prevented.

### F05 — N03 has a supported backup explanation

The context identifies BACKUP-10 on support-app at 16:10 UTC, targeting 203.0.113.10. B01 records that job starting; N03 shares its job ID and destination; B02 records completion. Together these support an approved-backup explanation for N03. The allowed action alone is not business approval. That backup does not explain N01, which has a different destination and earlier timestamp.

### F06 — Authorization and human identity remain unresolved

The context permits support exports but supplies no ticket or approval for this export. A missing approval record is not proof that approval never existed. Approval for internal use would not itself authorize an external transfer. The records identify an account/session rather than the person using it. No independent user confirmation or historical sign-in baseline is available.

## Proposed next actions

These are recommendations developed in the exercise. They have not been performed on an actual system.

1. Preserve the identity, VPN, application, network, IPS and scheduler records with source timestamps and protected originals. If available in a real authorized investigation, preserve the export and relevant endpoint artifacts as well. Record acquisition details and hashes; analyze working copies.
2. Request the support ticket, export authorization and any permission to send records to the external destination. Verify business purpose and destination ownership through an independent approved channel.
3. Obtain endpoint file-access and process-to-network telemetry, plus transfer records or destination-side evidence where authorized. Seek a direct link between export-017.json and N01, including whether a partial transfer occurred.
4. Have the incident lead assess proportionate session or egress restrictions if continuing exposure is suspected, with collection authority, service impact and evidence preservation considered. Do not describe these proposed controls as deployed.

A partial unauthorized transfer could expose data; checking only whether the entire file arrived would be insufficient.

## Outcome and remaining limits

The guided exercise produced an evidence-linked summary and timeline, not a confirmed breach determination. No measured loss, malicious actor, endpoint process or file-transfer linkage was established. No containment or recovery was executed. The original worksheet remains an optional independent retry; this report does not imply every worksheet response was completed unaided.

## Reproduction notes

Read E01 and E02, retain their original timestamps and sort events by their timezone-aware UTC equivalents. UTC−07:00 timestamps convert by adding seven hours; explicitly UTC timestamps stay unchanged. Match event IDs, session IDs, hosts and job IDs, then check each finding against its cited records. The assistant used Python standard-library JSON parsing, timezone conversion and SHA-256 hashing for preparation and validation, not a forensic tool suite.
