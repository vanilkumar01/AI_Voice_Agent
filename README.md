# Home Credit AI Voice Agent --- Loan Against Property (LAP) Qualification

## Project Overview

This project describes an AI voice agent designed to conduct preliminary
qualification conversations for a Home Credit Loan Against Property
(LAP) offer of up to ₹75 lakh.

The agent verifies the customer's identity, explains the offer, collects
eligibility details, handles exceptions, and routes the conversation to
the appropriate closing flow.

## Objectives

-   Build a professional AI voice agent.
-   Collect and validate seven required eligibility data points.
-   Apply the defined eligibility rules consistently.
-   Handle interruptions and answers provided out of order.
-   Identify existing-loan and loan-transfer requests.
-   Handle busy customers and callback requests.
-   Test the agent using structured scenarios and real call evidence.

## Platform and Configuration

-   **Voice platform:** Retell AI
-   **Agent type:** Conversation Flow Agent
-   **Agent name:** Kumar
-   **Language:** Indian English, subject to the selected voice's
    availability and capabilities
-   **System prompt:** `system_prompt.txt`

The exact model, voice, agent ID, and published URL should be documented
in `VoiceAgentPlatform/agent_platform_config.txt` after configuration.

## Project Structure

``` text
AIVoiceAgentAssignment/
├── system_prompt.txt
├── README.md
├── VoiceAgentPlatform/
│   └── agent_platform_config.txt
├── test_scenarios/
│   ├── agricultural_property.txt
│   ├── busy_customer.txt
│   ├── cash_income.txt
│   ├── eligible_customer.txt
│   ├── existing_loan.txt
│   ├── loan_above_75_lakh.txt
│   └── out_of_order_answers.txt
├── call_recording/
│   └── recording_links.txt
├── transcripts/
│   └── call_transcript.txt
└── brief_test_results/
    └── test_results.xlsx
```

## Conversation Workflow

1.  **Welcome and identity verification:** Confirm that the intended
    customer is speaking before discussing loan details.
2.  **Offer presentation:** Explain the LAP offer of up to ₹75 lakh and
    ask whether the customer wishes to continue.
3.  **Eligibility collection:** Collect the seven required data points.
4.  **Evaluation and exception handling:** Apply the eligibility rules
    and identify loan-transfer, disqualification, callback, and
    incomplete-information cases.
5.  **Closing:** Deliver the appropriate message and end the call.

## Eligibility Rules

The agent must collect these seven data points:

1.  Property type
2.  Ownership status
3.  Availability of original property documents
4.  Requested loan amount
5.  Occupation and income mode
6.  Estimated current property market value
7.  Requested repayment tenure

The specified rules are:

-   Residential, commercial, and industrial property types are eligible;
    agricultural property is not eligible.
-   Sole and joint ownership are acceptable.
-   Original property documents must be available.
-   The maximum requested amount is ₹75 lakh. If a customer requests
    more, offer the maximum and continue only with their consent.
-   Salaried and self-employed customers are acceptable, but income must
    be received through a bank.
-   Record the customer's estimated property market value. Do not invent
    a minimum or maximum threshold.
-   Repayment tenure must be between 3 and 15 years inclusive.
-   Existing property-loan transfer or EMI-reduction requests must be
    routed to the loan-transfer handling path rather than continuing
    fresh-loan qualification.

Preliminary qualification is not final loan approval. Final approval
remains subject to the lender's verification and assessment.

## Test Scenarios

The `test_scenarios/` directory contains scenarios for:

1.  Eligible customer
2.  Agricultural property
3.  Cash income
4.  Existing loan or EMI reduction
5.  Loan amount above ₹75 lakh
6.  Busy customer and callback request
7.  Answers provided out of order

Run each scenario using the configured agent. Compare the observed
behavior against the expected result in the relevant test file.

## Test Results

Record results in `brief_test_results/test_results.xlsx`. Recommended
columns:

-   Test ID
-   Scenario
-   Expected result
-   Actual result
-   Status
-   Recording link
-   Notes

Use `NOT RUN` until a scenario has actually been tested. Mark a test
`PASS` or `FAIL` only after comparing the actual behavior with the
expected behavior.

## Call Recordings and Transcripts

-   Store actual recording links in
    `call_recording/recording_links.txt`.
-   Store actual transcripts in `transcripts/call_transcript.txt`.
-   Make sure each recording and transcript is associated with the
    correct test case.
-   Verify that shared links open for the intended reviewer.
-   Follow applicable consent, privacy, and recording requirements. Do
    not include unauthorized personal or financial information.

Do not insert fabricated recording URLs or transcripts.

## Setup and Testing

1.  Create a Conversation Flow Agent in Retell AI.
2.  Configure the agent's voice and supported language.
3.  Add the instructions from `system_prompt.txt`.
4.  Configure the welcome, offer, eligibility, logic, exception, and
    closing nodes.
5.  Confirm that each transition leads to the correct destination.
6.  Test every scenario in `test_scenarios/`.
7.  Review actual recordings, transcripts, and extracted outcomes.
8.  Correct any failures and rerun the affected scenarios.
9.  Publish only after verifying the workflow.

A system prompt alone does not guarantee correct branching. Mandatory
rules must also be represented and tested in the configured conversation
flow.

## Configuration Details

-   **Agent URL:** \[Add actual URL\]
-   **Agent ID:** \[Add actual ID\]
-   **Voice selected:** \[Add actual voice\]
-   **Date tested:** \[Add actual date\]
-   **Project status:** In development / Testing / Published

Replace the placeholders with actual details before submission.

## Conclusion

This project demonstrates the design and testing of an AI voice agent
for structured Loan Against Property qualification. The final submission
should include the deployed prompt, platform configuration, scenario
definitions, genuine recordings, actual transcripts, and completed test
results.
