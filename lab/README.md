# Synthetic incident analysis exercise

**Status: guided analysis documented in a case report and UTC timeline. The discussion included assistant coaching; no independent assessment or real investigation is claimed.** All accounts, addresses, events and quantities are fictional. This exercise was created on October 20, 2026 as a new portfolio extension; it was not part of the original CS631 submission.

## Analysis outputs

- [Incident report](incident-report.md): accepted case summary, evidence-linked findings, limitations and proposed next actions.
- [UTC timeline](timeline.md): all 13 source events with original timestamps and interpretation.

## Practice or repeat the exercise

You are reviewing suspicious remote access to a fictional support application. Decide which activity needs investigation, which activity has a documented benign explanation, and what the available records cannot establish.

1. Read [the event log](events-readable.md) and [context](context.md).
2. Complete [the analyst worksheet](analyst-worksheet.md). Start with questions 1–3.
3. Cite event IDs for each conclusion. Keep observations separate from interpretations.
4. After reviewing your answers, complete a timeline and an incident report using the repository templates.

## Evidence files

- [Original synthetic events](data/events.jsonl): 13 JSON records, one per line.
- [Synthetic context](data/context.json): known assets, approved backup and deliberate evidence gaps.
- [SHA-256 manifest](SHA256SUMS.txt): hashes calculated after file generation, not hashes of acquired real-world evidence.

The readable log is a convenience view in supplied order. The record timestamps use both UTC and UTC−07:00. Preserve original timestamps when normalizing. Assume synchronized clocks as stated in the context.

The answer key is withheld from the learner package. There is no code to execute, cloud service to provision, or paid tool required. The generator and structural checks were performed by the assistant; they do not establish your analytical performance.

## Completion criteria

A completed independent retry should identify the relevant session, distinguish separate traffic flows, test the backup explanation and avoid unsupported attribution or data-theft claims. A final report must cite the evidence and describe its gaps. Describe the current activity as a guided synthetic log-analysis exercise. It does not establish independent forensic-tool use or real incident response.
