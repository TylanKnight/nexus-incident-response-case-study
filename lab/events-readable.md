# Synthetic event log

All records are fictional. Original timestamp offsets are preserved. See the separate context before drawing conclusions.

## A01 — sign_in_failed

```text
timestamp: 2026-10-20T08:55:00-07:00
source: identity
account: support.demo
source_ip: 198.51.100.23
reason: incorrect_password
```

## A02 — sign_in_failed

```text
timestamp: 2026-10-20T08:56:00-07:00
source: identity
account: support.demo
source_ip: 198.51.100.23
reason: incorrect_password
```

## A03 — sign_in_success

```text
timestamp: 2026-10-20T09:00:00-07:00
source: identity
account: support.demo
source_ip: 198.51.100.23
session_id: S-104
mfa: not_required
```

## A04 — session_assigned

```text
timestamp: 2026-10-20T16:00:05+00:00
source: vpn
account: support.demo
session_id: S-104
assigned_ip: 192.0.2.44
```

## A05 — sign_in_success

```text
timestamp: 2026-10-20T09:02:00-07:00
source: identity
account: ops.demo
source_ip: 203.0.113.20
session_id: S-105
mfa: passed
```

## P01 — records_viewed

```text
timestamp: 2026-10-20T16:04:00+00:00
source: application
account: support.demo
session_id: S-104
source_ip: 192.0.2.44
host: support-app
record_count: 12
```

## P02 — export_created

```text
timestamp: 2026-10-20T16:06:00+00:00
source: application
account: support.demo
session_id: S-104
host: support-app
artifact: export-017.json
record_count: 1200
bytes: 480000
```

## N01 — outbound_flow

```text
timestamp: 2026-10-20T16:07:00+00:00
source: network
host: support-app
source_ip: 192.0.2.60
destination_ip: 203.0.113.77
destination_port: 443
action: allowed
bytes_out: 510000
process_id: None
content_visible: False
```

## N02 — signature_alert

```text
timestamp: 2026-10-20T09:08:00-07:00
source: ips
source_ip: 198.51.100.23
destination_ip: 192.0.2.80
destination_port: 443
action: blocked
rule_id: LAB-401
flow_id: F-202
```

## B01 — job_started

```text
timestamp: 2026-10-20T16:10:00+00:00
source: scheduler
host: support-app
job_id: BACKUP-10
account: backup.demo
destination_ip: 203.0.113.10
```

## N03 — outbound_flow

```text
timestamp: 2026-10-20T16:11:00+00:00
source: network
host: support-app
source_ip: 192.0.2.60
destination_ip: 203.0.113.10
destination_port: 443
action: allowed
bytes_out: 15000000
job_id: BACKUP-10
content_visible: False
```

## B02 — job_completed

```text
timestamp: 2026-10-20T16:12:00+00:00
source: scheduler
host: support-app
job_id: BACKUP-10
result: success
```

## A06 — session_ended

```text
timestamp: 2026-10-20T09:15:00-07:00
source: vpn
account: support.demo
session_id: S-104
assigned_ip: 192.0.2.44
```
