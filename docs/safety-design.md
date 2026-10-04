# Safety design

CareContext's intended scope is patient education based on clinical context. Clinical validation is pending.

## Implemented controls

| Control | Application | Limit |
| --- | --- | --- |
| Education and physician-guidance instructions | Generation prompts | Prompt instructions do not guarantee in-scope output |
| Medication source checks | Summary workflow, before teach-back | Targeted checks do not validate all generated statements |
| Urgency rules | Before chat generation | Red matches bypass generation; clinical coverage requires validation |
| Longitudinal medication state | Dossier merge and rebuild | Depends on extraction quality and source completeness |
| Structured output handling | JSON-generating tasks | Parseability does not establish clinical correctness |
| Patient identifier filtering | Patient-context retrieval | Filtering must be paired with verified access controls |

The urgency logic is clinician-informed and pending clinical validation. No universal post-generation clinical approval mechanism is claimed.

## Demonstration data

Public demonstrations will use reviewed synthetic cases. Real medical records, identifiers, or care questions about an actual person should not be submitted to the demonstration service.

The implementation contains identifier-removal utilities, but these do not establish complete de-identification across input paths. Public demonstrations therefore require synthetic inputs from the start, including any material used for screenshots or recordings.

## Validation boundary

The system is not presented as clinically validated triage, a diagnostic or prescribing service, or a replacement for a care team. Safety evaluation must assess both missed problems and incorrect escalations, as well as the behavior of explanations outside their intended scope.

[Evaluation plan](evaluation.md) · [Back to CareContext](../README.md)
