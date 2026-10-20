# Synthetic case context

All times have explicit offsets. Assume source clocks are synchronized.

| Address | Meaning in this exercise |
|---|---|
| 192.0.2.44 | VPN address assigned to session S-104 |
| 192.0.2.60 | Support application server |
| 192.0.2.80 | Separate public gateway |
| 203.0.113.10 | Approved backup destination |
| 203.0.113.77 | Not listed in the provided approved destination register; maliciousness is unknown |

The approved job BACKUP-10 runs on support-app at 16:10 UTC and sends data to 203.0.113.10. Support staff may export records. No approval record or support ticket for export-017.json is supplied.

Missing evidence includes endpoint process telemetry, outbound payloads, independent user confirmation, a historical sign-in baseline, and a trace connecting the exported file to an outbound transfer. Missing evidence is a limitation, not proof that an action did or did not happen.
