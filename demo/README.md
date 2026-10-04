# CareContext demo

**Status: currently offline.** The Google Cloud application is paused to control hosting costs.

[Application address](https://carecontext-291933096366.us-central1.run.app)

A recorded walkthrough, screenshots, and downloadable synthetic cases are planned. They are not available in this release.

## Planned walkthrough

The demonstration will follow a synthetic patient across two encounters: an initial explanation, a medication-state update, a teach-back interaction, and follow-up questions using accumulated context.

| Scenario | What to inspect |
| --- | --- |
| Encounter explanation | Whether the summary preserves the source guidance |
| Medication update | Whether considered, current, and stopped states stay distinct |
| Teach-back | How an answer changes the recorded comprehension context |
| Follow-up question | How prior encounters and retrieved references enter the response |
| Out-of-scope request | Whether the response stays within the educational boundary |

Each case will include synthetic source material and suggested questions. Recorded outputs will be labeled as recorded; future live inference will be labeled as live. Demonstrations will show actual application behavior rather than illustrative outputs presented as results.

## Before interactive access opens

The demo environment will need isolated synthetic records, verified access controls, and usage limits. No real patient data should be uploaded. Clinical collaborators will review the selected cases before public release.

[Back to CareContext](../README.md)
