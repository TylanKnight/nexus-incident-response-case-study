# Scenario and investigation scope

## Fictional organization

Nexus develops consoles and games and operates an online platform with multiplayer, cloud saves, messaging and a digital storefront. Its assumed environment includes employee endpoints, remote access, development repositories, production services, cloud resources and leased data centers. None of these resources was deployed for this portfolio.

Protected assets include player records, payment references, employee information, source code, build credentials and signing keys. The original report assumes that an external provider processes card payments. The scenario's approximate 2,500 employees and five million registered players describe fictional scale, not users served by the author.

## Investigation questions

| Question | Evidence the plan would seek | What remains insufficient alone |
|---|---|---|
| Did stolen credentials enable access? | Identity-provider and remote-access events correlated with server sessions | A successful login does not identify the human user |
| Did a suspicious client execute? | Download history, process relationships, execution artifacts and endpoint records | A matching filename does not establish execution |
| Did access expand to development or production? | Permissions, firewall decisions, repository records and host authentication | A network connection does not establish authorized or malicious intent |
| Was information transferred? | Staging artifacts, process activity and transfer records | File creation alone does not prove exfiltration |
| Was an outage caused by abuse? | Request patterns, resource utilization, provider flow records and release baselines | An availability incident does not prove data theft |

## Scope boundaries

The plan covers company-managed systems and authorized service records. Examination of player-owned devices requires separate authority. Proposed remote, local, client and denial-of-service incidents are distinct planning examples and may overlap. They must not be combined into a supposedly observed attack chain.

Source: original report pp. 2–16. This page condenses those scenarios; it contains no collected incident evidence.
