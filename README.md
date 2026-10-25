# HelpDesk AI: GenAI Functional QA Portfolio

## 1. Project Overview

This project demonstrates a structured quality assurance approach for a fictional Generative AI customer support assistant called **HelpDesk AI**.

The assistant is designed to answer customer questions about returns, refunds, shipping, and order status.

The objective is to assess the assistant's functional correctness, adherence to defined business rules, handling of ambiguous questions, and reliability when responding to unsupported or irrelevant requests.

**Project type:** GenAI Functional QA  
**Application:** Fictional customer support chatbot  
**Testing focus:** Functional testing, negative testing, ambiguity handling, instruction following, and hallucination-risk assessment

### Results at a Glance
- **20 GenAI functional test scenarios** executed against a locally hosted HelpDesk AI prototype.
- **5 key testing areas:** Policy compliance, ambiguity handling, instruction following, hallucination risk, and unsupported transaction claims.
- **4 Pass, 9 Partial Pass, and 7 Fail** Based on the documented expected behaviour and observed model responses.
- **Evidence-backed assessments:** Prompts, model responses, observations, and a test coverage matrix are available in this repository.
- **Key risk areas observed:** Fabricated order and tracking information, unsupported refund confirmations, and failure to enforce defined return policies.

**Important:** These results describe the behaviour of the tested local model in this fictional test environment. They do not represent production defect rates or results from a deployed customer-support system.

### Test Environment

- **Local model runner:** Ollama
- **Model:** `gemma3:4b`
- **Application under test:** No production application; prompts were tested directly against the local language model using fictional HelpDesk AI instructions.
- **Execution date:** 13 October 2026

## 2. Business Rules

HelpDesk AI is expected to follow these predefined business rules:

1. Customers can request returns within 30 days.
2. Refunds are processed within 5 to 7 business days after approval.
3. Standard shipping takes 3 to 5 business days.
4. Order-specific status enquiries require an order number.
5. The assistant must not invent order details, confirm unverified transactions, or make unsupported policy exceptions.
6. When a question lacks necessary information, the assistant should ask for clarification rather than assume missing details.
7. For questions outside its supported scope, the assistant should communicate its limitations instead of fabricating an answer.

### Business Rule Clarifications

For portfolio test design, the following assumptions will be used unless a scenario explicitly tests for ambiguity:

- The 30-day return window includes day 30; requests after day 30 are outside the standard window.
- Refund timelines are measured in business days, not calendar days.
- Shipping estimates refer to business days.
- Order status cannot be confirmed without an order number and access to a reliable order-status source.
- The assistant must distinguish general policy information from information specific to an individual customer's order.

These rules define the expected behaviour against which test scenarios will be designed.

## 3. Testing Scope

### In Scope

- Positive functional scenarios
- Negative and boundary scenarios
- Ambiguous and incomplete user queries
- Business-rule adherence
- Unsupported claims and hallucination risks
- Instruction-following behaviour
- Irrelevant and out-of-scope questions
- Clarity and consistency of responses

### Out of Scope

- Production infrastructure and performance testing
- Security penetration testing
- Verification of real customer accounts or transactions
- Claims about model accuracy across a production dataset
- Automated test execution unless separately implemented and documented

## 4. Portfolio Artifacts

This repository contains the following artifacts from the GenAI functional QA exercise:

**Test coverage matrix:** Scenario-level coverage, testing areas, and assessment summaries.

**Test observations:** Test objectives, business rules, inputs, expected behaviour, actual responses, assessments, and observations for the documented test cases.

**Prompt and response evidence:** Individual prompt and model-response files for the corresponding test cases.

**Execution evidence:** Captured local model interaction logs where available.

**Defined test scope and business rules:** The expected HelpDesk AI behaviour used as the basis for assessment.

The observations document records the QA assessment of each scenario. The Pass, Partial Pass, and Fail classifications represent outcomes against the defined expectations; they should not be interpreted as confirmed defects in a production application.

## 5. Test Approach

Each scenario will define the user input, expected behaviour, validation criteria, and execution status where applicable.

Test outcomes will distinguish between:

- **Designed:** A test scenario has been documented.
- **Executed:** The scenario has actually been run against the identified application or test environment.
- **Simulated:** An illustrative result has been created for demonstration purposes and is not evidence of an actual application execution.

Only observed results will be reported as executed test outcomes. Any illustrative defects or results will be explicitly labelled as simulated.

## 6. Test Execution Summary

A total of 20 functional test cases were executed against the local HelpDesk AI chatbot using the configured fictional support policies and the `gemma3:4b` model through Ollama.

| Assessment | Count | Percentage |
|---|---:|---:|
| Pass | 4 | 20% |
| Partial Pass | 9 | 45% |
| Fail | 7 | 35% |
| **Total** | **20** | **100%** |

### Key Observations

- **Pass:** The response met the defined expected behaviour for the test scenario.
- **Partial Pass:** The response met some expectations but had gaps or inconsistencies.
- **Fail:** The response violated one or more defined business rules or expected behaviours.

The test suite evaluates functional correctness, policy adherence, ambiguity handling, instruction following, and the risk of unsupported or fabricated information in model responses.

### Evidence

- Test case objectives, inputs, expected behaviour, actual responses, assessments, and observations are documented in [`evidence/observations.md`](evidence/observations.md).
- Separate prompt and response evidence files are available for TC-GEN-012 through TC-GEN-020.
- TC-GEN-001 through TC-GEN-011 have their prompt and response details recorded within the observations document.

### Test Coverage Matrix

The [test coverage matrix](docs/test-coverage-matrix.md) provides a consolidated view of all 20 test cases, their primary coverage areas, and their recorded assessments.

### Scope Note

These results represent a portfolio test run against a local model and a fictional support policy. They should not be interpreted as production-system defects or as a benchmark of all LLMs.

## 7. QA Value Demonstrated

This exercise demonstrates a structured approach to evaluating GenAI-powered customer-support behaviour against defined business rules and expected outcomes.

The assessment focuses on whether the assistant:
- Applies business policies consistently, including return eligibility and refund timelines.
- Requests clarification when required information is missing or ambiguous.
- Avoids fabricating order status, tracking details, refund confirmations, or system capabilities.
- Follows defined instructions when faced with conflicting requests or customer pressure.
- Communicates limitations instead of presenting unverified information as fact.

For each scenario, the documented evidence supports a review of the observed response against the expected behaviour. This approach can help QA teams identify risky response patterns and prioritise further validation before a GenAI feature is released.

**Potential QA deliverables for similar engagements:** Scenario design, expected-behaviour criteria, prompt-based functional evaluation, evidence capture, risk-focused findings, and a test summary. These are examples of services this portfolio approach can support, not claims of completed client engagements.

## 8. Project Status

The initial 20-scenario GenAI functional QA exercise has been executed and documented. The repository includes the test coverage matrix, observations, and supporting prompt/response evidence.

The portfolio is being refined to improve the clarity of findings, traceability between scenarios and evidence, and presentation of QA value. Results remain specific to the local model and fictional HelpDesk AI scenario described in this repository.

## 9. Disclaimer

HelpDesk AI is a fictional application created for demonstrating QA methodology. This project does not represent testing performed for an actual customer or production system.
