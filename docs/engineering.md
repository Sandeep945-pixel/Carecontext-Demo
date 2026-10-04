# Engineering decisions

CareContext translates a clinical education problem into an application with explicit context, retrieval, generation, and persistence responsibilities.

## Preserve state across encounters

A medication mentioned during a visit may be current, stopped, or only under consideration. Treating every mention as an active medication can introduce errors into later explanations.

The dossier maintains these distinctions and merges new encounters into existing context. Rebuilding from remaining visits after a deletion addresses a related consistency problem: derived context should reflect the encounters that still exist.

## Keep individual context and reference knowledge distinct

General medical references and a patient's history answer different questions. The retrieval layer uses separate collections for those sources and combines relevant results at query time. The health graph supplies structured relationships in addition to vector similarity.

This separation supports inspection of where context came from. It does not, by itself, establish that a generated claim is supported; source attribution needs its own evaluation.

## Apply checks at the relevant workflow stage

Medication checking occurs after summary generation and before teach-back generation, so questions are generated from the checked summary. The chat workflow separately evaluates urgency rules before calling the model; a red-rule match follows a fixed response path.

These controls address specific failure modes. Prompt constraints guide other educational responses, and clinical validation of their behavior remains pending.

## Treat structured generation as an application dependency

The model wrapper requests JSON for extraction and other structured tasks, handles parsing failures, and retries with additional output allowance. Completion diagnostics help distinguish truncated responses from successful generation.

This is an engineering reliability measure. Syntactically valid output still requires checks for meaning and source fidelity.

## Capture comprehension as context

Teach-back connects the explanation workflow to feedback on patient understanding. That information can be included in later context rather than assuming that generating a summary establishes comprehension. Whether this improves understanding is a research question for evaluation.

## Separate product implementation from public presentation

The public repository explains design and scope while the implementation remains private. Demonstrations will use synthetic cases, allowing the product workflow to be shown without publishing patient records or application internals.

[Back to CareContext](../README.md)
