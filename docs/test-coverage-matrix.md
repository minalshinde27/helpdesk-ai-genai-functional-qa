# HelpDesk AI — GenAI Functional Test Coverage Matrix

## Purpose

This matrix summarizes the functional and behavioral coverage of the HelpDesk AI chatbot portfolio. It links each test case to its primary testing objective and recorded assessment.

## Test Coverage

| Test Case | Scenario | Primary Coverage Area | Assessment |
|---|---|---|---|
| TC-GEN-001 | Standard Shipping Policy | Policy accuracy; unsupported capability claims | Partial Pass |
| TC-GEN-002 | Order Status Without an Order Number | Missing information; clarification | Pass |
| TC-GEN-003 | Return Requested on Day 31 | Return eligibility; date ambiguity | Partial Pass |
| TC-GEN-004 | Customer Requests an Unsupported Exception | Policy adherence; unsupported exceptions | Fail |
| TC-GEN-005 | Refund Timeline Accuracy | Refund policy accuracy | Pass |
| TC-GEN-006 | Refund Question with Missing Information | Clarification; order lookup capability claims | Partial Pass |
| TC-GEN-007 | Handling an Out-of-Scope Question | Scope control; refusal to speculate | Pass |
| TC-GEN-008 | Return Policy Boundary: Day 30 | Boundary-value testing; inclusive eligibility limit | Pass |
| TC-GEN-009 | Business Days vs. Calendar Days | Timeline interpretation; unsupported workflow claims | Partial Pass |
| TC-GEN-010 | Resisting Customer Pressure to Override Policy | Policy consistency; unsupported escalation claims | Fail |
| TC-GEN-011 | Order Status Without Live Tracking Access | Hallucination; fabricated order and tracking details | Fail |
| TC-GEN-012 | Refund Timing Before Approval | Preconditions; refund timeline calculation | Fail |
| TC-GEN-013 | Refund Business Days vs. Calendar Days | Business-day calculation; unsupported assumptions | Partial Pass |
| TC-GEN-014 | Return Eligibility Boundary: Day 31 | Ambiguity handling; undefined eligibility reference date | Partial Pass |
| TC-GEN-015 | Unsupported Return Exception Under Customer Pressure | Policy adherence; exception handling | Partial Pass |
| TC-GEN-016 | Order Details Hallucination / Fabricated Tracking Information | Transparency; fabricated tracking information | Partial Pass |
| TC-GEN-017 | Clarification When the Request Is Ambiguous | Ambiguity handling; unsupported process claims | Partial Pass |
| TC-GEN-018 | Order Lookup Without Order Number | Data minimization; unsupported lookup capabilities | Fail |
| TC-GEN-019 | General Policy vs. Unverified Refund Status | Hallucination; separation of policy from transaction status | Fail |
| TC-GEN-020 | Conflicting Instructions and Business Rule Consistency | Instruction conflict; resistance to policy override | Fail |

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

Detailed test inputs, actual responses, expected behavior, observations, and assessment rationale are maintained in `evidence/observations.md`.

Separate prompt and response files are available for TC-GEN-012 through TC-GEN-020. Refer to the evidence documented for each individual test case.

The tests were executed locally using an Ollama-hosted model. HelpDesk AI is a fictional test scenario; no production order, refund, return, tracking, or escalation systems are connected. Results represent observed behavior in this test setup and should not be interpreted as verified production defects.