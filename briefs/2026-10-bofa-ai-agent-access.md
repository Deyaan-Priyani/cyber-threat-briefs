# Bank of America and AI agents: who gets to act on your account?

**Context:** October 2026 reporting and public bank guidance  
**Last reviewed:** November 13, 2026

## TL;DR

Bank of America warns customers against sharing banking passwords with
third-party AI agents and asks them to understand the access they grant.
This brief examines that access risk. The bank's warning does not establish
that Bank of America suffered a breach.
[Bank of America guidance](https://web.bankofamerica.com/en/security/library/agentic-ai)

## Classification and impact

- **Classification:** An AI-agent access and credential-risk event. The issue
  is what a tool can do after a customer connects it to a financial account.
- **Severity:** Potentially high, in my assessment, because banking access is
  sensitive. This is a risk judgment, not a scored software vulnerability.
- **Primary target:** Customer financial accounts and the permissions given to
  outside tools.
- **Known impact:** The reviewed guidance does not provide a confirmed Bank of
  America victim count or financial loss. It describes precautions and customer
  responsibilities. [Bank of America guidance](https://web.bankofamerica.com/en/security/library/agentic-ai)

## How the risk works

An AI agent can perform steps for a user rather than simply answer questions.
Bank of America explains that connecting an outside agent may permit actions
on the customer's behalf. Customers should review what information a service
can access, how it uses that information and what actions it is authorized to
perform. [Bank of America guidance](https://web.bankofamerica.com/en/security/library/agentic-ai)

Axios reported third-party AI agents accessing U.S. bank accounts, sometimes
acting beyond users' instructions.
[Industry reporting, October 22](https://www.axios.com/2026/10/22/ai-agents-banks-unauthorized-accounts-access)

That industry report and the bank's warning are different evidence. Together
they raise a useful question for this brief: does successful login also mean
every action an agent takes is appropriate? My answer is that access permission
and permission for a particular task should be evaluated separately.

## Basic MITRE ATT&CK mapping

| Tactic: goal | Technique ID and name | How it applies |
| --- | --- | --- |
| Initial Access: enter through an existing account | [T1078 — Valid Accounts](https://attack.mitre.org/techniques/T1078/) | Conceptual comparison: real credentials can allow software to enter an account without exploiting a software bug. |

T1078 describes adversaries abusing accounts. A customer-approved agent is not
automatically an adversary. This comparison highlights an access-control risk,
not a confirmed malicious technique used against Bank of America.

## What defenders can learn

My recommendation is to give an agent only the permissions its task needs and
require human approval for sensitive actions. OAuth provides a framework for
limited third-party access, including permission scopes. A scope is a limit
on what access is granted. This is a general design lesson, not a claim about
Bank of America's specific implementation.
[OAuth specification](https://www.rfc-editor.org/rfc/rfc6749#section-3.3)

The central lesson is simple: handing a tool a password can give it more access
than the user intended. Clear permission limits make that risk easier to manage.
