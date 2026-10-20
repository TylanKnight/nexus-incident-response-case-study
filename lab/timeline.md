# Synthetic case timeline

Case NEXUS-LAB-001. Prepared October 20, 2026 as part of a guided exercise with Tylan Knight. The assistant normalized timestamps and assembled this table from the unchanged synthetic input files. This is not a real incident timeline or an independently completed forensic acquisition.

Sources: [event records](data/events.jsonl), [readable log](events-readable.md) and [case context](data/context.json). Event IDs identify individual input records. All rows are on October 20, 2026. The context assumes synchronized clocks; normalization changes the display timezone, not the source timestamp.

| Event ID | Original timestamp | UTC timestamp | Recorded observation | Interpretation and limitation |
|---|---|---|---|---|
| A01 | 2026-10-20T08:55:00-07:00 | 2026-10-20 15:55:00 UTC | Failed sign-in for support.demo from 198.51.100.23; incorrect password. | A failed attempt does not establish compromise. |
| A02 | 2026-10-20T08:56:00-07:00 | 2026-10-20 15:56:00 UTC | Second failed sign-in for support.demo from the same address. | Repeated failures warrant review; legitimate mistakes remain possible. |
| A03 | 2026-10-20T09:00:00-07:00 | 2026-10-20 16:00:00 UTC | Successful sign-in for support.demo; session S-104; MFA not required. | Authentication succeeded. The person using the account is unknown. |
| A04 | 2026-10-20T16:00:05+00:00 | 2026-10-20 16:00:05 UTC | VPN assigned 192.0.2.44 to support.demo session S-104. | Connects the sign-in session to the address recorded in P01. |
| A05 | 2026-10-20T09:02:00-07:00 | 2026-10-20 16:02:00 UTC | ops.demo signed in as session S-105; MFA passed. | A separate account/session; no supplied linkage to the export. |
| P01 | 2026-10-20T16:04:00+00:00 | 2026-10-20 16:04:00 UTC | support.demo session S-104 viewed 12 records on support-app from 192.0.2.44. | Account, session and assigned address correlate with A03/A04. |
| P02 | 2026-10-20T16:06:00+00:00 | 2026-10-20 16:06:00 UTC | S-104 created export-017.json on support-app: 1,200 records, 480,000 bytes. | Export creation is recorded. Actual export contents and transfer are not supplied. |
| N01 | 2026-10-20T16:07:00+00:00 | 2026-10-20 16:07:00 UTC | support-app (192.0.2.60) sent recorded outbound traffic to 203.0.113.77:443; allowed; 510,000 bytes out. | Same host and close timing as P02 are clues. No process or payload linkage establishes that the export was sent. |
| N02 | 2026-10-20T09:08:00-07:00 | 2026-10-20 16:08:00 UTC | IPS blocked traffic from 198.51.100.23 to public-gateway (192.0.2.80):443; flow F-202. | Separate connection from N01. This block does not change N01’s allowed result. |
| B01 | 2026-10-20T16:10:00+00:00 | 2026-10-20 16:10:00 UTC | BACKUP-10 started on support-app under backup.demo, targeting 203.0.113.10. | Matches the approved job and scheduled time in context.json. |
| N03 | 2026-10-20T16:11:00+00:00 | 2026-10-20 16:11:00 UTC | support-app sent traffic to 203.0.113.10:443; allowed; 15,000,000 bytes out; job BACKUP-10. | Job, host, destination and timing support the approved-backup explanation. This does not explain N01. |
| B02 | 2026-10-20T16:12:00+00:00 | 2026-10-20 16:12:00 UTC | Scheduler recorded BACKUP-10 completed successfully. | Corroborates job completion; it is not a restore or content-integrity test. |
| A06 | 2026-10-20T09:15:00-07:00 | 2026-10-20 16:15:00 UTC | VPN session S-104 ended; assigned address was 192.0.2.44. | Session end does not establish containment or explain who used it. |

## Correlation summary

- A03 and A04 share S-104. P01 shares the account/session and assigned VPN address; P02 shares the account/session and application host.
- P02 precedes N01 by one minute on the same host. The recorded byte counts differ and do not identify the transferred content.
- N02 concerns different source/destination endpoints from N01. Its blocked result applies to its own recorded connection.
- B01, N03 and B02 share BACKUP-10 and are consistent with the approved backup context. N01 has a different destination and occurs before that job starts.

Sequence and shared fields support correlation, not proof of causation, malicious intent or human identity.
