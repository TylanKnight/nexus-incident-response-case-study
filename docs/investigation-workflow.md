# Investigation and response workflow

This is a proposed workflow adapted from the academic report, not a record of actions performed.

## 1. Validate the alert and define authority

Record the alert, affected asset, account, business function, suspected impact and known collection authority. Assign an incident lead. Establish who can approve actions that interrupt service. Separate an observed event from an analyst's hypothesis.

The plan assigns alert validation to monitoring analysts, preservation and interpretation to a forensic examiner, and approved isolation and restoration to service administrators. The incident lead coordinates priorities. Legal/privacy staff address collection authority and notification questions; communications staff coordinate approved updates.

## 2. Preserve evidence alongside containment

Prioritize volatile information when feasible and justified. Document live-collection commands, tools, time, known changes and limitations. Urgent containment may precede full acquisition; record what evidence may be lost and why the decision was necessary.

Assign evidence identifiers. Record collection times with offsets, the source clock and known clock differences. Hash acquired files with a documented algorithm and preserve protected originals. Use working copies for analysis and suitable write protection for offline media. Record transfers, access and storage locations in the templates.

Hash agreement supports unchanged content between the compared copies. It does not establish that the source was accurate, benign or created by a particular person.

## 3. Examine the relevant artifacts

| Evidence class | Proposed examination |
|---|---|
| Identity and remote access | Authentication results, session identifiers, assigned addresses, account changes and privileges |
| Endpoint | Process relationships, file creation, persistence, removable-device history and execution artifacts |
| Application and repository | Record requests, exports, access history and changes to development assets |
| Network | IDS/IPS action, source/destination, ports, protocol, rule version, DNS, flows and firewall decisions |
| Availability | Resource consumption, request rates, failed health checks, recent deployments and provider counters |

Resolve address translation and VPN assignments before attributing traffic to a device. Retain sensor configuration and rule versions where available. Record missing logs, packet loss and encrypted traffic as visibility limits.

## 4. Correlate and test explanations

Normalize time without discarding original timestamps. Connect events through session, device, account, flow and artifact identifiers. Compare suspicious activity with approved work, backups, software updates and legitimate demand.

For a possible service exploit, seek evidence connecting the request to execution. For possible lateral movement, correlate network reachability, host logons and the permissions in force. For suspected transfer, identify both the staged material and corroborating transfer evidence. An IPS block describes that event; it does not prove earlier requests were blocked.

## 5. Contain and restore

Select actions according to the demonstrated access path or service impact: account/session restrictions, host isolation, targeted filtering, configuration correction or provider assistance. Record decision authority, expected impact and rollback arrangements.

Restore from an appropriate clean state and validate legitimate service behavior. Recheck the relevant control and monitor for renewed activity. Do not close an incident solely because the service responds again.

## 6. Report and improve

Document findings, supporting evidence IDs, alternative explanations and unresolved questions. Assign each corrective action an owner and acceptance requirement. In the source plan, a review within ten business days after stabilization and a retest within 30 days of implementation are proposed targets, not achieved response times.

Source: original report pp. 12–20 and 22–23.
