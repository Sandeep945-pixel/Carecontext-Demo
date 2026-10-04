# Evaluation

Development and testing are ongoing. Clinical and operational benchmark results are not published in this repository.

## Engineering regression tests

The private implementation includes test cases for:

- distinguishing current medications from negated or considered medications;
- stopping and subsequently reinstating medications;
- deduplication and overlapping medication names;
- rebuilding context after visit deletion;
- checking a mocked generated summary against source medication information.

These describe the scope of existing test definitions. No passing test count or clinical outcome is reported here.

## Planned assessment

| Question | Method | Reporting requirements |
| --- | --- | --- |
| Does a summary preserve encounter meaning? | Claim-level review against synthetic source encounters | Error categories, denominators, and adjudication |
| Are medication states preserved across visits? | Encounter sequences with explicit expected states | Scenario coverage and regression results |
| Are explanations supported by their references? | Review retrieved sources against generated claims | Source versions and unsupported claims |
| Do responses remain within educational scope? | Clinician-reviewed in-scope and out-of-scope cases | Review criteria, disagreements, and failure examples |
| Do urgency rules behave appropriately? | Clinician-approved boundary and counterexample cases | Missed matches and false matches |
| Are explanations understandable? | Readability analysis and a separately designed comprehension study | Study design and participant outcomes |
| What are the operational costs and delays? | Controlled synthetic workloads | Model version, workload, concurrency, latency percentiles, errors, and cost |

Readability is not a substitute for demonstrated comprehension. Synthetic benchmark performance is not evidence of clinical effectiveness. Future results will identify the system version, dataset provenance, sample size, method, and limitations.

[Back to CareContext](../README.md)
