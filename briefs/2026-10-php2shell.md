# PHP2Shell: web requests that can take over a server

**Disclosure:** October 21, 2026  
**Last reviewed:** November 13, 2026

## TL;DR

PHP2Shell refers to two serious flaws in PHP, which powers websites.
A specially crafted web request can exploit these flaws to run code on an
affected server without logging in. PHP published security updates on October
21. [PHP advisory](https://www.php.net/archive/2026.php)

## Classification and impact

- **Classification:** Remote code execution, meaning someone can make another
  computer run their code over a network.
- **Severity:** Critical. Unit 42 reports a CVSS 4.0 score of **9.2** for each flaw.
- **Primary target:** Internet-facing services using vulnerable PHP software.
- **Known exploitation:** On October 29, Unit 42 reported active exploitation
  against internet-exposed PAN-OS management interfaces. This is evidence of
  real attacks, beyond the existence of vulnerable software.
  [Unit 42 threat brief](https://origin-unit42.paloaltonetworks.com/cve-2026-109618-cve-2026-109619/)

## How it worked

The first flaw, **CVE-2026-109618**, concerns PHP's response to running out of
memory. Processing stops before some request data is fully prepared. Cleanup
code can then treat that unfinished data as valid.

The second flaw, **CVE-2026-109619**, involves old references to memory that has
already been released. A later request handled by the same worker can reuse
that stale information. Both problems can turn normal request handling into an
opportunity to execute code. [PHP advisory](https://www.php.net/archive/2026.php)

Exploitation was not equally reliable everywhere. In its October 27 report,
Wiz described attempts in its own monitoring that had not completed the full
attack. That earlier, limited observation does not contradict Unit 42's later
report of active exploitation elsewhere.
[Wiz research](https://www.wiz.io/blog/php2shell-exploitation-so-far)

## Basic MITRE ATT&CK mapping

| Tactic: attacker's goal | Technique ID and name | How it applies |
| --- | --- | --- |
| Initial Access: get into a system | [T1190 — Exploit Public-Facing Application](https://attack.mitre.org/techniques/T1190/) | A crafted request targets vulnerable PHP exposed through a web service. |

This is my mapping of the entry method. It does not establish what an attacker
did after gaining access.

## What defenders can learn

My recommended first step is to identify exposed PHP services and confirm
their patch status with the software owner. PHP's initial fixed releases were
8.5.12, 8.4.27, 8.3.36 and 8.2.35. Distribution vendors may supply backported
fixes, so version numbers alone can be misleading.
[PHP advisory](https://www.php.net/archive/2026.php)

For an analyst, a suspicious request is a reason to investigate. It is not
automatic proof of a successful takeover. Keep exposure, attempted exploitation
and confirmed compromise separate when reporting the incident.
