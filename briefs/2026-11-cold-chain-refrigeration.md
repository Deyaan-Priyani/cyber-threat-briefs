# Grocery refrigeration attacks: when a cyberattack changes the temperature

**Reported waves:** October and November 2026  
**Last reviewed:** November 13, 2026

## TL;DR

Attackers targeted refrigeration controls used by grocery stores and cold
storage facilities. Changing those controls can warm products or keep equipment
in heating and defrost cycles, creating inventory and safety risks. U.S.
agencies issued a joint warning on November 5.
[Government advisory](https://www.ic3.gov/CSA/2026/261105.pdf)

## Classification and impact

- **Classification:** An operational technology (OT) attack. OT means systems
  that monitor or control physical equipment, such as refrigerators.
- **Severity:** High, in my assessment, because interference can damage goods
  and interrupt essential operations. This is not a vendor vulnerability score.
- **Primary target:** Electronic refrigeration controllers, especially those
  reachable from the internet.
- **Potential impact:** Unsafe temperatures, lost stock, equipment hazards and
  loss of temperature visibility. The government warning describes these
  consequences as possible effects, not outcomes verified at every facility.
  [Government advisory](https://www.ic3.gov/CSA/2026/261105.pdf)

## How it worked

A refrigeration controller manages temperatures and defrost schedules. Attackers
can exploit unpatched software or weak settings to change how equipment runs.
The joint advisory lists authentication bypass, code injection and weak
configurations as possible entry paths.
[Government advisory](https://www.ic3.gov/CSA/2026/261105.pdf)

Sekoia's November 10 investigation describes altered settings at hundreds of
European supermarkets and reports food spoilage and business interruption. Its
research focuses specifically on Danfoss controllers, so those findings should
not be applied automatically to every refrigeration incident.
[Sekoia research](https://www.sekoia.com/blog/the-cold-chain-on-fire-unpatched-danfoss-controllers-exploited)

Censys described attacks in France during October and a second wave across
European countries in early November. Its research also measured **6,695
internet-exposed controllers falling to 3,124**, a **53% decrease**, between
October 9 and November 5. Those numbers measure exposure, not the number of
compromised devices. The data does not explain why each controller disappeared
from the internet. [Censys research](https://censys.com/wp-content/uploads/ARC_EuroFridge_SITREP-2026-11_Dark-2.pdf)

## Basic MITRE ATT&CK mapping

| Tactic: attacker's goal | Technique ID and name | How it applies |
| --- | --- | --- |
| Impact: disrupt a physical process | [T0831 — Manipulation of Control](https://attack.mitre.org/techniques/T0831/) | Changing temperature or defrost settings interferes with how refrigeration operates. |

This technique comes from ATT&CK for industrial control systems. It fits the
physical manipulation described in the reporting. It does not identify the
attacker or establish the same entry method at every site.

## What defenders can learn

The government recommends removing unnecessary internet access, securing remote
connections, using strong authentication and keeping controllers updated.
[Government advisory](https://www.ic3.gov/CSA/2026/261105.pdf)

My main takeaway is that a security team should involve equipment operators
when investigating unusual control changes. A technical alert may represent a
real temperature change that staff need to check immediately. The practical
question is both whether someone accessed the controller and whether the goods
are still being stored safely.
