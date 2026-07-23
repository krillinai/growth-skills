# Customer Research Contract

## Minimum Context

Capture these fields independently:

- decision, owner, decision date, and actions the research could change;
- primary research question and bounded subquestions;
- product, customer job, current alternative, market, language, locale, product surface, and lifecycle state;
- unit: individual, role, household, workspace, account, buying committee, seller, buyer, creator, or another declared participant;
- inclusion, exclusion, identification, and disqualification rules available at recruitment time;
- hypotheses, counterhypotheses, known evidence, contradictory evidence, and unavailable evidence;
- method and reason it fits the question;
- recruitment frame, source, sample targets, variation, incentive, contact owner, and nonresponse risk;
- consent, recording, transcription, translation, quote use, storage, access, retention, and withdrawal conditions;
- source IDs, capture dates, artifact types, owners, completeness, and limitations;
- coding, synthesis, count, segment, and decision rules.

Public information can support desk research, public-language analysis, alternatives, review themes, and a draft research plan. It cannot establish private motives, prevalence, customer identity, retained value, willingness to pay, or causal mechanisms.

## Source And Claim Ledger

For each evidence unit include:

| Field | Requirement |
| --- | --- |
| Source ID | Stable attributable identifier |
| Source type | Interview, transcript, survey, review, support, sales, observation, public artifact, or behavioral record |
| Context | Participant criteria, market, role, lifecycle state, prompt, and surrounding situation |
| Capture | Date, owner, language, consent, recording, transcription, and translation state |
| Evidence | Exact quote, response, observed behavior, or bounded paraphrase |
| Status | `verified`, `inferred`, `unavailable`, or `not applicable` |
| Interpretation | Code, theme, hypothesis, or decision relevance |
| Limitation | Selection, memory, prompting, missing context, translation, nonresponse, or measurement risk |

Verification applies to the artifact and attribution, not automatically to the participant's explanation or its population prevalence.

## Consent And Privacy

Use the minimum data required for the legitimate research decision. Separate consent for participation, recording, transcription, internal analysis, quoting, external publication, follow-up, and incentives where applicable. Do not infer consent from an existing customer relationship or public profile.

Prefer pseudonymous IDs. Exclude raw names, email addresses, phone numbers, private URLs, credentials, payment data, unrelated payloads, and sensitive attributes unless necessary and approved. Preserve withdrawal and quote restrictions. Do not claim deletion, anonymization, payment, scheduling, contact, or publication already occurred.

## Output Boundary

If evidence is missing, return the contract, method choice, recruitment and evidence plan, and precise unanswered questions. Do not fabricate participants, quotes, sample sizes, frequencies, themes, or customer certainty to complete a report.
