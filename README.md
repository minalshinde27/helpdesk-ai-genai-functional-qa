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

The repository contains the following artifacts from the GenAI functional QA exercise:

- **[Test coverage matrix](docs/test-coverage-matrix.md):** Coverage areas, test case references, and recorded assessments for all 20 scenarios.
- **[Test observations](evidence/observations.md):** Test objectives, business rules, inputs, expected behaviour, actual responses, assessments, and supporting observations.
- **Prompt and response evidence:** Separate evidence files for TC-GEN-012 through TC-GEN-020; details for TC-GEN-001 through TC-GEN-011 are recorded in the observations document.
- **Execution evidence:** Local model interaction logs where available.
- **Test instructions and business rules:** The defined behaviour used to evaluate the fictional HelpDesk AI assistant.

Assessment labels reflect observed responses against the portfolio's defined expectations. They are not confirmed defects in a production application.

## 5. Test Approach

Each scenario will define the user input, expected behaviour, validation criteria, and execution status where applicable.

Test outcomes will distinguish between:

- **Designed:** A test scenario has been documented.
- **Executed:** The scenario has actually been run against the identified application or test environment.
- **Simulated:** An illustrative result has been created for demonstration purposes and is not evidence of an actual application execution.

Only observed results will be reported as executed test outcomes. Any illustrative defects or results will be explicitly labelled as simulated.

## 6. Test Execution Summary

A total of 20 functional test cases were executed against the locally hosted `gemma3:4b` model through Ollama, using the fictional HelpDesk AI instructions and business rules.

| Assessment | Count | Percentage |
|---|---:|---:|
| Pass | 4 | 20% |
| Partial Pass | 9 | 45% |
| Fail | 7 | 35% |
| **Total** | **20** | **100%** |

### Key Findings

The test run identified response patterns requiring further validation, including:

- Fabricated order or tracking information.
- Unsupported refund confirmations and transaction claims.
- Inconsistent application of defined return policies.
- Gaps in handling ambiguous requests and communicating limitations.

These classifications reflect the observed responses against the defined expected behaviour. They are specific to this test run and should not be interpreted as production defect rates or a benchmark of all language models.

### Evidence and Coverage

- [Detailed test observations](evidence/observations.md) — inputs, expected behaviour, actual responses, assessments, and rationale.
- [Test coverage matrix](docs/test-coverage-matrix.md) — consolidated coverage and assessment status for all 20 scenarios.
- Separate prompt and response files are available for TC-GEN-012 through TC-GEN-020. Details for TC-GEN-001 through TC-GEN-011 are included in the observations document.

## 7. QA Value Demonstrated

This portfolio demonstrates how structured functional QA can be applied to GenAI features before release. Rather than judging responses only by whether they sound plausible, the approach evaluates them against explicit business rules, expected behaviour, and defined risk scenarios.

### QA Activities Demonstrated

- **Business-rule validation:** Check whether responses consistently apply defined policies, eligibility conditions, and timelines.
- **Negative and boundary testing:** Probe invalid requests, policy boundaries, missing information, and unsupported assumptions.
- **Ambiguity and instruction-following evaluation:** Assess whether the assistant asks appropriate clarifying questions and follows its defined instructions when requests are incomplete or conflicting.
- **Hallucination-risk assessment:** Identify unsupported claims, fabricated order or tracking details, and unverified transaction confirmations.
- **Evidence-based assessment:** Record the input, expected behaviour, observed response, assessment, and rationale so findings can be reviewed and reproduced within the same test setup.

### Potential QA Deliverables

For a scoped GenAI functional QA engagement, deliverables could include:

1. A risk-based test scenario suite mapped to agreed requirements and business rules.
2. Expected-behaviour criteria and positive, negative, boundary, and ambiguity-focused test inputs.
3. Recorded prompts, model responses, and execution evidence where available.
4. An assessment log with evidence-backed findings and risk observations.
5. A coverage summary and recommendations for further validation.

The exact scope and deliverables would be agreed based on the feature, available test environment, and client requirements. This portfolio demonstrates the approach using a fictional application and a locally hosted model; it does not claim prior paid-client delivery or production-system testing.

## 8. Project Status

The initial 20-scenario GenAI functional QA exercise has been executed and documented against the locally hosted `gemma3:4b` model using fictional HelpDesk AI instructions.

The repository includes the test coverage matrix, detailed observations, and supporting prompt/response evidence for the documented scenarios. The portfolio is being refined to improve the clarity and presentation of findings while preserving traceability and transparency about the test environment.

All reported results are specific to this test setup and are not claims of production-system testing or paid-client experience.

## 9. Disclaimer

HelpDesk AI is a fictional application created for demonstrating QA methodology. This project does not represent testing performed for an actual customer or production system.
