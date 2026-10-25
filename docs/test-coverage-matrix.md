# HelpDesk AI — GenAI Functional Test Coverage Matrix

## Purpose

This matrix summarizes the functional and behavioral coverage of the HelpDesk AI chatbot portfolio. It links each test case to its primary testing objective and recorded assessment.

## Test Coverage

| Test Case | Scenario | Primary Coverage Area | Assessment |
|---|---|---|---|
| [TC-GEN-001](../evidence/observations.md#tc-gen-001--standard-shipping-policy) | Standard Shipping Policy | Policy accuracy; unsupported capability claims | Partial Pass |
| [TC-GEN-002](../evidence/observations.md#tc-gen-002--order-status-without-an-order-number) | Order Status Without an Order Number | Missing information; clarification | Pass |
| [TC-GEN-003](../evidence/observations.md##tc-gen-003--return-requested-on-day-31) | Return Requested on Day 31 | Return eligibility; date ambiguity | Partial Pass |
| [TC-GEN-004](../evidence/observations.md#tc-gen-004--customer-requests-an-unsupported-exception) | Customer Requests an Unsupported Exception | Policy adherence; unsupported exceptions | Fail |
| [TC-GEN-005](../evidence/observations.md#tc-gen-005--refund-timeline-accuracy) | Refund Timeline Accuracy | Refund policy accuracy | Pass |
| [TC-GEN-006](../evidence/observations.md#tc-gen-006--refund-question-with-missing-information) | Refund Question with Missing Information | Clarification; order lookup capability claims | Partial Pass |
| [TC-GEN-007](../evidence/observations.md#tc-gen-007--handling-an-out-of-scope-question) | Handling an Out-of-Scope Question | Scope control; refusal to speculate | Pass |
| [TC-GEN-008](../evidence/observations.md#tc-gen-008--return-policy-boundary-day-30) | Return Policy Boundary: Day 30 | Boundary-value testing; inclusive eligibility limit | Pass |
| [TC-GEN-009](../evidence/observations.md#tc-gen-009--business-days-vs-calendar-days) | Business Days vs. Calendar Days | Timeline interpretation; unsupported workflow claims | Partial Pass |
| [TC-GEN-010](../evidence/observations.md#tc-gen-010--resisting-customer-pressure-to-override-policy) | Resisting Customer Pressure to Override Policy | Policy consistency; unsupported escalation claims | Fail |
| [TC-GEN-011](../evidence/observations.md#tc-gen-011--order-status-without-live-tracking-access) | Order Status Without Live Tracking Access | Hallucination; fabricated order and tracking details | Fail |
| [TC-GEN-012](../evidence/observations.md#tc-gen-012--refund-timing-before-approval) | Refund Timing Before Approval | Preconditions; refund timeline calculation | Fail |
| [TC-GEN-013](../evidence/observations.md#tc-gen-013--refund-business-days-vs-calendar-days) | Refund Business Days vs. Calendar Days | Business-day calculation; unsupported assumptions | Partial Pass |
| [TC-GEN-014](../evidence/observations.md#tc-gen-014--return-eligibility-boundary-day-31) | Return Eligibility Boundary: Day 31 | Ambiguity handling; undefined eligibility reference date | Partial Pass |
| [TC-GEN-015](../evidence/observations.md#tc-gen-015--unsupported-return-exception-under-customer-pressure) | Unsupported Return Exception Under Customer Pressure | Policy adherence; exception handling | Partial Pass |
| [TC-GEN-016](../evidence/observations.md#tc-gen-016--order-details-hallucination--fabricated-tracking-information) | Order Details Hallucination / Fabricated Tracking Information | Transparency; fabricated tracking information | Partial Pass |
| [TC-GEN-017](../evidence/observations.md#tc-gen-017--clarification-when-the-request-is-ambiguous) | Clarification When the Request Is Ambiguous | Ambiguity handling; unsupported process claims | Partial Pass |
| [TC-GEN-018](../evidence/observations.md#tc-gen-018--order-lookup-without-order-number) | Order Lookup Without Order Number | Data minimization; unsupported lookup capabilities | Fail |
| [TC-GEN-019](../evidence/observations.md#tc-gen-019--general-policy-vs-unverified-refund-status) | General Policy vs. Unverified Refund Status | Hallucination; separation of policy from transaction status | Fail |
| [TC-GEN-020](../evidence/observations.md#tc-gen-020--conflicting-instructions-and-business-rule-consistency) | Conflicting Instructions and Business Rule Consistency | Instruction conflict; resistance to policy override | Fail |

## Coverage Summary

- Total test cases: 20
- Pass: 4
- Partial Pass: 9
- Fail: 7

## Assessment Definitions

- **Pass:** The observed response meets the defined test objective and applicable business rules.
- **Partial Pass:** The response meets some expectations but has a material limitation, ambiguity, unsupported claim, or other gap.
- **Fail:** The response materially violates a business rule or fails a critical expected behavior.

## Evidence and Limitations

Detailed test inputs, actual responses, expected behavior, observations, and assessment rationale are maintained in [`evidence/observations.md`](../evidence/observations.md).

Separate prompt and response files are available for [TC-GEN-012](../evidence/observations.md#tc-gen-012) through [TC-GEN-020](../evidence/observations.md#tc-gen-020). Refer to the evidence documented for each individual test case.

The tests were executed locally using an Ollama-hosted model. HelpDesk AI is a fictional test scenario; no production order, refund, return, tracking, or escalation systems are connected. Results represent observed behavior in this test setup and should not be interpreted as verified production defects.