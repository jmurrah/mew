# Risk and Regulation Evidence

- **Cluster ID:** `risk_regulation`
- **Python module:** `risk_regulation.py`
- **Layer:** Market evidence

Shared rules: [Evidence Contract](../../docs/core/evidence-contract.md).
Field catalog: [Cluster Records](../../docs/schemas/cluster-records.md#risk-regulation).
Authority registry: [Authority Sources](../../docs/sources/providers/authorities.md).

## Purpose

Surface inspectable evidence that a candidate behavior may require legal,
regulatory, privacy, safety, platform, API, or operational investigation. Explain
what caused each concern, what authority supports it, and what remains unknown.
Do not determine legality, compliance, or whether anything should be built.

## Scope

- Candidate descriptions, product pages, help/onboarding copy, permissions,
  claims, integrations, APIs, and traceable evidence from other clusters.
- Regulated domains/actions, decision criticality, consequence of error,
  sensitive data, vulnerable users, dependencies, marketplaces, and support
  complexity.
- Requested and inferred data with separate provenance.
- Trigger-based mapping to official regulator, platform, marketplace, and
  government sources.
- Conditional retrieval of policy, guidance, rulemaking, device, or dependency
  documents.
- Separate regulatory, harm, privacy, platform, and support signals.
- Explicit prohibition, approval, registration, legal-entity, and human-review
  flags when authoritative evidence supports them.

## Out of Scope

- Legal advice or definitive applicability conclusions.
- State-by-state or country-by-country matrices inferred from short descriptions.
- Automatic rejection, approval, ranking, or one risk/opportunity score.
- Enforcement, lawsuit, compliance-cost, support-hours, or store-acceptance
  probabilities.
- Definitive scraping legality or arbitrary Terms-of-Service interpretation.
- Broad semantic search across all regulation or the open web.
- Duplicate acquisition of competitor reviews owned by another cluster.
- Comprehensive enforcement similarity, privacy-policy compliance, or legal
  classification in v1.

## Research Unit

One risk claim links:

1. Exact candidate-side trigger.
2. Risk family and tag.
3. Candidate behavior, data, user, platform, integration, or support scope.
4. One or more authority-side records.
5. Evidence direction.
6. Applicability unknowns and manual-review reason.

Evidence direction is one of `prohibits`, `permits_with_conditions`,
`requires_disclosure`, `requires_approval`, `requires_support`,
`highlights_enforcement`, or `unclear`.

## Evidence Model

Required distinctions:

- Domain mention versus action performed.
- Regulatory sensitivity versus consequence of error.
- Sensitive data versus automatic HIPAA applicability.
- Requested versus inferred data.
- First-party versus third-party tracking/sharing.
- Policy versus enforcement history.
- Technical access versus legal permission.
- Platform dependency versus marketplace eligibility.
- High risk versus explicit prohibition.
- Inherent risk versus optional feature or implementation choice.

Authority review priority is official regulator, official platform policy,
official marketplace guide, statute/court/case, qualified legal analysis,
operator material, then community discussion. Priority does not prove currency
or applicability.

### Risk Families

Regulated-domain tags:

```text
MEDICAL
MENTAL_HEALTH
REPRODUCTIVE_HEALTH
LEGAL
INVESTING
LENDING
TAX
CHILD_DIRECTED
GAMBLING
CRYPTO
AIR_TRAVEL
HEALTH_RECORDS
REGULATED_INDUSTRY_OTHER
```

Accuracy/harm tags:

```text
DIAGNOSIS
DETECTION
TREATMENT
DOSAGE
PERSONALIZED_ADVICE
OFFICIAL_FILING
OFFICIAL_SUBMISSION
LEGAL_DISCRETION
FINANCIAL_RECOMMENDATION
SAFETY_CRITICAL_OUTPUT
PHYSICAL_HARM
HIGH_ACCURACY_REQUIRED
MISLEADING_CLAIM
```

Sensitive-data families include identity, financial, health, location,
children, authentication, device/communications, genetic, sex-life,
orientation, political, and religious data. Preserve specific requested and
inferred tags rather than only category counts.

Initial detailed taxonomy:

```text
IDENTITY: NAME, EMAIL, PHONE, ADDRESS, DOB, GOV_ID, SSN
FINANCIAL: BANK_ACCOUNT, CREDIT_CARD, INCOME, CREDIT_SCORE,
  TRANSACTIONS, INVESTMENT_HOLDINGS, PAYMENT_DATA
HEALTH: DIAGNOSES, MEDICATIONS, SYMPTOMS, PREGNANCY_DATA,
  MENTAL_HEALTH_DATA, BIOMETRICS, MEDICAL_RECORDS
LOCATION: PRECISE_LOCATION, LOCATION_HISTORY
CHILDREN: CHILD_IDENTITY, CHILD_LOCATION, SCHOOL_INFORMATION,
  PARENTAL_INFORMATION
AUTHENTICATION: PASSWORD, OAUTH_TOKEN, API_KEY
DEVICE_OR_COMMUNICATIONS: CONTACTS, MESSAGES, SMS_CALL_DATA,
  MICROPHONE, CAMERA, PHOTOS, AUDIO, INSTALLED_APP_INVENTORY
OTHER_SPECIAL_CATEGORY: GENETIC, SEX_LIFE, SEXUAL_ORIENTATION,
  POLITICAL, RELIGIOUS
```

Platform/API tags include declarations, legal-entity rules, privacy policy,
support contact, account deletion, review/resubmission, policy-change,
permissions, payment dependency, public API, rate limit, paid/revocable access,
automated-access restriction, login wall, retention/redistribution, API
change/termination rights, and anti-bot observations.

Initial platform/API tags:

```text
APP_REVIEW_REQUIRED
DECLARATION_REQUIRED
LEGAL_ENTITY_REQUIRED
PRIVACY_POLICY_REQUIRED
SUPPORT_CONTACT_REQUIRED
ACCOUNT_DELETION_REQUIRED
RESUBMISSION_REQUIRED
MARKETPLACE_DELIST_RISK
PLATFORM_POLICY_CHANGE_RISK
PERMISSION_BREADTH_RISK
PAYMENT_POLICY_DEPENDENCY
KNOWN_RESTRICTED_CATEGORY
NO_PUBLIC_API
OFFICIAL_API_AVAILABLE
RATE_LIMITED_API
PAID_API
REVOKABLE_ACCESS
NO_SCRAPING_CLAUSE
AUTOMATED_ACCESS_RESTRICTED
LOGIN_WALL
PUBLIC_DATA_ONLY
CONTRACT_RISK
IP_RISK
CFAA_PUBLIC_ACCESS_ARGUMENT
ACCESS_CAN_BE_REVOKED
DATA_RETENTION_RESTRICTION
REDISTRIBUTION_RESTRICTION
API_CHANGE_RIGHT
API_TERMINATION_RIGHT
ANTI_BOT_MEASURES_PRESENT
```

Support tags include moderation, child-safety escalation, privacy requests,
deletion, incident response, billing disputes, review queues, urgent correction,
and human exception handling.

Initial support tags:

```text
UGC_MODERATION
SOCIAL_MODERATION
CHILD_SAFETY_ESCALATION
ACCOUNT_DELETION
PRIVACY_REQUESTS
INCIDENT_RESPONSE
BILLING_DISPUTE
REVIEW_QUEUE_DELAY
MANUAL_REVIEW_REQUIRED
TIMELY_SUPPORT_EXPECTED
URGENT_CORRECTION
HUMAN_EXCEPTION_QUEUE
```

## Observable Fields

- Risk claim, candidate, candidate evidence, authority evidence, dependency, and
  source-policy IDs.
- Candidate trigger text, source URL, product surface, function, data/user scope,
  and core/optional dependency.
- Authority title, URL, publisher, source type, jurisdiction/platform,
  publication/update/retrieval time, excerpt, hash, and prior version.
- Evidence direction, explicit requirement language, and source conflicts.
- Official API existence, access mode, authentication, quota/rate-limit facts,
  payment, commercial-use, retention, redistribution, change, and termination
  terms when directly visible.
- Account, billing, sync, integration, hardware, real-time data, UGC, moderation,
  import/export, and multi-device complexity indicators.

## Derived Fields

- Domain/action tags and decision criticality: `informational`,
  `workflow_assist`, `user_decision_support`, `official_submission`, or
  `physical_world_impact`.
- Consequence-of-error, regulatory-sensitivity, privacy, platform-dependency,
  and support-burden signals: `LOW`, `MEDIUM`, `HIGH`, or `UNKNOWN`.
- Requested/inferred sensitive-data and vulnerable-user tags.
- Risk dependency: `inherent`, `optional_feature`, `implementation_choice`, or
  `unknown`.
- Explicit prohibition, license/clearance, legal-entity, human-review, and legal-
  review flags.
- Classification method/rule version/confidence, missing inputs, and manual state.

`disqualifying_condition_flag` means inspect a possible hard stop; it never
removes a candidate automatically.

## Analysis

### Classification Order

1. Exact deterministic phrase or field.
2. Curated synonym and pattern rules.
3. Product/workflow context.
4. Trigger-to-authority registry.
5. Optional semantic or local model support.
6. Optional traceable model classification.
7. Human review for ambiguity or high consequence.

Planning favors mostly deterministic local classification, a smaller curated
authority registry, and selective live enrichment. The earlier 70/20/10 split is
a design heuristic, not a measured target.

### Component Signals

- Regulatory sensitivity rises when regulated domains combine with individualized
  diagnosis, treatment, advice, filing, discretion, authorization, or entity
  requirements.
- Consequence of error is high for plausible physical harm, dosage, diagnosis,
  crisis response, legal-rights loss, official filing, or material financial loss.
- Privacy risk rises when sensitive/inferred data or minors combine with sharing,
  tracking, syncing, SDKs, weak predictability, or weak manageability.
- Platform dependency is high when one revocable/reviewed/rate-limited external
  dependency is essential.
- Support burden is high for moderation, child safety, urgent correction,
  privacy requests, incident response, or prompt marketplace duties.

Keep components separate. Missing authority evidence never means low risk.

### Failure Modes

- Sensitive topic mistaken for regulated action.
- Health data mistaken for automatic HIPAA applicability.
- Public access mistaken for legal permission.
- Educational finance/tax/legal content mistaken for personalized advice or
  official submission.
- High risk mistaken for prohibition or predicted store rejection.
- Inferred data, third-party SDKs, support duties, and optional risky features
  missed.
- Current access assumed permanent.
- Policy history overwritten instead of versioned.

## Source Applicability

Initial work should use deterministic rules, a curated 20–40-document authority
registry, direct official retrieval, Apple/Google policy, and static IRS mapping.
Trigger conditional Federal Register, openFDA, GitHub, named dependency terms,
or one verified web-search provider only when needed.

See [Authority Sources](../../docs/sources/providers/authorities.md),
[Search Providers](../../docs/sources/providers/search.md), and other provider
references under [Source Index](../../docs/sources/index.md).

Federal Register and openFDA enrich a triggered question; they do not classify a
candidate. eCFR and Regulations.gov are later targeted sources. Reddit is not a
required risk source.

## Guardrails

- Every risk claim preserves candidate and authority evidence.
- Use source hierarchy for review priority, not truth by fiat.
- Set hard-stop flags only from explicit high-authority language and always
  preserve applicability uncertainty.
- Never infer a ban from severity.
- Version policy captures instead of overwriting them.
- Reuse other cluster records through stable IDs and shared orchestration.

## Output Contract

Future output should contain risk claim records, candidate risk summaries,
dependency records, and authority-registry references. Each claim exposes
trigger, direction, component severity, authority excerpt, unknowns, and manual
review. Output feeds section 8 of the investigation profile and never acts as a
gatekeeper.

## Open Questions

- Which verified authority documents form the initial registry?
- Which jurisdictions beyond US federal and major platforms enter first?
- What candidate inputs reliably expose features, permissions, SDKs, and
  dependencies?
- What confidence threshold routes deterministic matches to review?
- How will optional-feature boundaries be supplied without turning risk work
  into product design?
- How will policy snapshots be versioned and deduplicated?
