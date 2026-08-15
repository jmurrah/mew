# Cluster Context: `risk_regulation`

This file stores durable design guidance for the Risk and Regulation Evidence
cluster. It models the supplied ideal specification and practical API-access
assessment. Neither input is collected market evidence, legal advice, or proof
that any rule applies to a future candidate.

## Identity

- **Cluster ID:** `risk_regulation`
- **Display name:** Risk and Regulation Evidence
- **Python module:** `risk_regulation.py`
- **Purpose:** Surface inspectable evidence that a candidate may require legal,
  regulatory, privacy, safety, platform, API, or operational investigation.
- **Decision role:** Help the user understand what caused each concern, how
  serious the signal may be, what authoritative material supports it, and what
  remains unknown. This cluster does not determine legality or compliance,
  choose opportunities, or recommend what to build.

## Core Research Question

For a candidate product behavior or opportunity:

1. What domain, action, output, data type, user population, distribution
   platform, integration method, or support obligation creates a risk signal?
2. Could incorrect output materially harm health, safety, finances, legal rights,
   official filings, or vulnerable users?
3. What sensitive data would the product request, derive, infer, sync, share, or
   expose to third-party code?
4. Does core value depend on another company's API, data, review process,
   permissions, marketplace, or mutable policy?
5. Does an authoritative source prohibit the behavior, permit it conditionally,
   require disclosure, require approval, require support, or merely suggest
   further review?
6. What paired raw records let a human audit the candidate-side trigger and the
   rule-side interpretation?

The useful output is a set of narrow risk claims with provenance. It is not a
legal conclusion, compliance checklist, predicted enforcement outcome, or
automatic rejection.

## Design Position

### Evidence Layer, Not Gatekeeper

Risk can be navigable, optional, or inherent. A high-risk signal may identify a
valuable niche with real obligations. A hard-stop-looking condition may depend
on facts not yet known. The cluster therefore surfaces evidence and review
reasons but never removes, ranks, or approves opportunities.

### Tangible Triggers Beat Generic Warnings

Prefer claims such as:

- patient-specific dosage recommendation detected;
- Google Play health declaration may be required;
- Apple regulated-service legal-entity policy matched;
- account creation appears to trigger an account-deletion obligation;
- anonymous chat appears to trigger ongoing moderation duties;
- core function depends on a revocable, rate-limited API;
- platform terms explicitly restrict automated access;
- IRS e-file authorization appears relevant to official transmission.

Avoid unsupported summaries such as `compliance risk`, `probably illegal`, or
`app stores may reject it`.

### Practical MVP Shape

The supplied practical assessment recommends an approximate design mix:

- 70% local deterministic classification;
- 20% curated authoritative-source matching;
- 10% selective live web or API enrichment.

These percentages are design heuristics, not measured performance targets. The
MVP goal is to detect evidence that a candidate deserves risk investigation,
not decide which laws apply.

## Scope

### Included

- Candidate-side product descriptions, listings, help text, onboarding copy,
  permissions, feature claims, API documentation, integration descriptions, and
  traceable evidence supplied by other clusters.
- Local multi-label detection of regulated domains, regulated actions, decision
  criticality, consequence of error, sensitive data, vulnerable users,
  third-party dependencies, marketplace surfaces, and support complexity.
- Requested and inferred data classifications with separate provenance.
- Curated mappings from strong triggers to official regulator, platform,
  marketplace, and government guidance.
- Conditional retrieval of official guidance, policy pages, API terms, rate
  limits, public rulemaking records, medical-device datasets, and selected
  platform issue data.
- Platform and marketplace conditions for Apple App Store, Google Play, Chrome
  Web Store, Slack Marketplace, Shopify App Store, Atlassian Marketplace, and
  other directly relevant surfaces.
- Technical and contractual access indicators: public/authenticated access,
  official API presence, quotas, payment, revocability, retention limits,
  redistribution limits, login walls, robots directives, anti-bot behavior, and
  explicit automated-access language.
- Support and operational obligations: moderation, child-safety escalation,
  privacy requests, account deletion, incident response, billing disputes,
  urgent corrections, manual exception queues, and marketplace responsiveness.
- Separate low/medium/high inspection signals for regulatory sensitivity,
  consequence of error, privacy sensitivity, platform dependency, and support
  burden, with raw inputs exposed.
- Explicit flags for prohibitions, approval or registration requirements, legal-
  entity requirements, and manual specialist review.
- Stable raw IDs, URLs, excerpts, dates, hashes, transformation rules, source
  hierarchy, evidence direction, confidence, uncertainty, and manual-review
  notes.

### Excluded or Deferred

- Legal advice; definitive conclusions about legality, compliance, liability,
  HIPAA, GDPR, state privacy laws, medical-device class, unauthorized practice
  of law, investment-adviser registration, licensure, or tax obligations.
- State-by-state or country-by-country applicability matrices inferred from a
  short candidate description.
- Automatic opportunity rejection, approval, ranking, go/no-go decisions,
  build plans, validation plans, or a single opaque opportunity score.
- Estimated lawsuit probability, enforcement probability, compliance cost,
  support hours per customer, or marketplace-acceptance probability.
- Definitive scraping legality. `robots.txt` and terms indicators remain
  technical or contractual evidence, not legal permission or prohibition.
- Automatic legal interpretation of arbitrary Terms of Service.
- Broad semantic search across the entire CFR or open web for every candidate.
- Comprehensive enforcement-case similarity and competitor privacy-policy
  compliance analysis in the MVP.
- Independent competitor-review acquisition already owned by another cluster.
  Cross-cluster reuse must occur through stable evidence IDs.
- GovInfo as an MVP source because it overlaps Federal Register and eCFR needs.
- Regulations.gov, CFPB complaint enrichment, comprehensive enforcement search,
  jurisdiction-specific investigation, and competitor privacy labels in v1.
- App-store reviews for arbitrary competitors through official owner-only APIs.
- Aggressive unauthenticated scraping or an MVP dependency on restricted Reddit
  access.

## Canonical Terminology

- **Candidate:** Opportunity, product concept, feature, or observed product
  behavior being investigated. Candidate description is input, not evidence
  that a law or policy applies.
- **Risk claim:** One auditable assertion connecting a candidate-side trigger to
  one risk tag and supporting external evidence.
- **Candidate-side trigger:** Exact text or observed behavior suggesting a risky
  action, domain, data type, audience, platform, integration, or obligation.
- **Authority-side evidence:** External policy, guidance, rule, case,
  enforcement record, or qualified analysis explaining why the trigger matters.
- **Planning context:** Supplied design and access guidance. It is not market or
  applicability evidence and receives no raw evidence ID.
- **Domain mention:** Candidate discusses a sensitive field without necessarily
  performing a regulated or high-consequence action.
- **Action performed:** Candidate claims to diagnose, treat, recommend, file,
  submit, decide, calculate, control, generate, or otherwise act for the user.
- **Decision criticality:** Functional impact level: `informational`,
  `workflow_assist`, `user_decision_support`, `official_submission`, or
  `physical_world_impact`.
- **Consequence of error:** Potential harm if output is wrong, kept separate from
  whether a rule applies.
- **Requested data:** Data the product explicitly asks for or accesses.
- **Inferred data:** Sensitive status or attribute derivable from behavior,
  inputs, correlations, or workflow even when not explicitly requested.
- **Vulnerable user:** User population for whom harm, consent, safety, or support
  needs may be elevated, including children, teens, patients, pregnant users,
  and users in mental-health contexts.
- **Risk dependency:** Whether concern is `inherent`, `optional_feature`,
  `implementation_choice`, or `unknown` relative to core value.
- **Evidence direction:** What source does: `prohibits`,
  `permits_with_conditions`, `requires_disclosure`, `requires_approval`,
  `requires_support`, `highlights_enforcement`, or `unclear`.
- **Regulatory sensitivity:** Inspection label for strength of regulated-domain,
  action, authorization, and entity signals; not a legal determination.
- **Platform dependency:** Degree to which launch or core operation relies on
  one platform's access, review, quota, policy, or continued permission.
- **Support burden:** Observable operational obligations and complexity, not an
  estimate of hours or staffing.
- **Hard-stop flag:** Explicit evidence of prohibition, required authorization,
  legal-entity constraint, or core access conflict. It always requires human
  review and never triggers automatic rejection.
- **Risk signal:** Explainable inspection label derived from named raw fields.
  It is not evidence, confidence in legality, or an opportunity score.

## Concepts That Must Remain Separate

### Topic Versus Function

A pregnancy journal, educational tax guide, legal glossary, or general finance
library may mention sensitive topics while remaining informational. Diagnosis,
dosage, personalized advice, legal discretion, official filing, and submission
are stronger action signals. Store `domain_mentioned` and `action_performed`
separately.

### Regulatory Sensitivity Versus Consequence of Error

Legal applicability can be unclear while harm from a wrong output is obvious.
Wrong movie recommendations and wrong insulin doses differ even before formal
classification. Preserve both components.

### Sensitive Data Versus HIPAA

Health data does not establish HIPAA applicability. Relationships with covered
entities and business associates matter. Non-HIPAA health products may still
raise FTC Act, Health Breach Notification Rule, platform, advertising, or
tracking issues. Record each possible family separately and preserve unknown
relationship facts.

### Requested Versus Inferred Data

A cycle predictor, mood journal, or symptom tracker may infer reproductive,
mental-health, or medical status without requesting a formal record. Record
explicit collection and workflow-based inference independently.

### First-Party Versus Third-Party Data Behavior

Advertising, analytics, tracking, and SDK behavior can create the meaningful
privacy risk. Record third-party code, sharing, cross-app identifiers, and
unknown SDK behavior instead of evaluating only first-party copy.

### Policy Versus Enforcement

Policy explains stated obligations. Enforcement records show priorities and
past action. Preserve distinct evidence subtypes; similarity to a candidate is
derived and uncertain.

### Technical Access Versus Legal Permission

Public access, a permissive `robots.txt`, or absence of anti-bot measures does
not grant commercial reuse rights. A disallow directive does not by itself
settle legality. Keep access mode, contract language, technical barriers, data
sensitivity, and legal analysis separate.

### Platform Dependency Versus Marketplace Eligibility

Dependency asks whether the product survives loss of access. Eligibility asks
whether category-specific listing or policy conditions apply. A product can be
API-dependent without store distribution, or store-dependent without a core
API integration.

### High Risk Versus Prohibition

High risk can mean allowed with declarations, disclosures, safeguards, review,
or support. A prohibition requires explicit source language. Never infer a ban
from severity alone.

### Inherent Versus Optional Risk

An insulin dosage recommendation is inherently tied to medical accuracy. A
pregnancy journal gains different risk if an optional diagnostic chatbot is
added. Record whether removing an optional feature preserves the underlying
job.

## Risk Families and Tags

### 1. Regulated Domain

Initial tags:

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

Domain tags are multi-valued. They trigger investigation, not applicability.

Strong candidate-side language includes diagnosis, treatment, symptom
interpretation, dosage, medications, medical measurements, fertility,
pregnancy, therapy, crisis support, investment recommendations, asset
allocation, trading, lending, tax filing, legal advice, jurisdiction-specific
rights, official documents, child-directed use, age gates, and parental control.

### 2. Accuracy and Harm

Initial tags:

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

Functional verbs and claimed outcomes outweigh category nouns. Detect whether
output is general education, workflow assistance, decision support, official
submission, or physical-world control.

Medical-device signals may include patient-specific analysis, treatment or
diagnostic output, dosage calculations, connections to medical devices, and
medical sensors. Report `fda_device_risk_signal`; never assert device class
unless describing a matched official record rather than classifying candidate.

Mental-health distinctions include education, mood tracking, meditation, peer
support, therapy, crisis detection, suicide/self-harm risk, diagnosis, and
treatment recommendations. Do not infer professional licensing obligations.

Legal distinctions include information, form filling, document generation from
answers, case-specific rights evaluation, strategy, and representation. Record
jurisdiction dependence and specialist-review need; do not decide unauthorized
practice of law.

Tax distinctions include education, calculation, personalized guidance, return
preparation, filing, and e-file transmission. Official transmission is strongest
trigger for static IRS authorization mapping.

### 3. Privacy and Data

Initial data taxonomy:

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

Store requested and inferred tags separately. Derived summaries may include:

```text
sensitive_data_categories_count
high_sensitivity_data_present
child_data_present
health_data_present
financial_data_present
identity_theft_data_present
sdk_data_sharing_present
privacy_predictability_signal
privacy_manageability_signal
```

Predictability asks whether users can reasonably foresee collection and use.
Manageability asks whether they can inspect, delete, or control it. These are
early-warning signals inspired by privacy engineering, not compliance tests.

### 4. Platform and Marketplace

Initial tags:

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
```

Target surfaces may include:

```text
APPLE_APP_STORE
GOOGLE_PLAY
CHROME_WEB_STORE
SLACK_MARKETPLACE
SHOPIFY_APP_STORE
ATLASSIAN_MARKETPLACE
```

Capture distribution concentration, integration concentration, review-time
dependency, re-review conditions, store-listing acquisition dependence,
security/privacy attestation, category declarations, legal-entity rules, public
API restrictions, and policy-change sensitivity.

Do not calculate marketplace acceptance probability.

### 5. API and Scraping

Initial tags:

```text
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

Required raw questions:

- Is access public, authenticated, partner API, private API, or unknown?
- Does an official API exist, and is it required for core value?
- What authentication, default quota, rate limit, payment, commercial-use,
  retention, redistribution, caching, deletion, or audit condition is visible?
- Do terms explicitly mention scraping, automated access, crawler, robot,
  harvesting, commercial use, redistribution, rate limits, retention, or
  deletion?
- What happens to product value if access is throttled, changed, or revoked?
- Are `robots.txt`, login walls, or anti-bot behavior observed?

Record factual indicators. Never set `scraping_legal = true/false`.

### 6. Support and Operations

Initial tags:

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

Local complexity indicators:

```text
requires_user_accounts
requires_password_recovery
requires_billing
requires_subscription
requires_cloud_sync
requires_external_integrations
requires_hardware
requires_real_time_data
requires_user_generated_content
requires_moderation
requires_data_import
requires_data_export
requires_multi_device_sync
```

UGC, anonymous interaction, random chat, child-directed use, urgent harm,
privacy-rights handling, and marketplace responsiveness can create high burden
even at low volume. Measure obligations and ticket complexity indicators, not
expected support hours.

When traceable review or complaint records already exist, possible bounded
counts include support problems, bugs, sync failures, billing problems, account
recovery, and data loss. Keep source, sample, time window, classification rule,
and raw IDs. Do not acquire the same reviews again inside this cluster.

## Unit of Analysis and Artifact Model

### Risk Claim Record

One row per candidate trigger, risk tag, and coherent authority mapping:

```text
risk_claim_id
opportunity_id
risk_checked_at
product_surface
candidate_evidence_id
candidate_source_url
candidate_trigger_text
trigger_type
risk_family
risk_tag
risk_dependency
applies_to
jurisdiction_or_platform
decision_criticality
consequence_of_error_signal
severity_signal
evidence_direction
authority_evidence_ids
authority_source_type
authority_title
authority_url
authority_publisher
authority_published_or_updated_at
authority_retrieved_at
authority_excerpt
authority_claim_summary
classification_method
classification_rule_version
classification_confidence
missing_inputs
manual_review_reason
manual_review_status
```

`applies_to` may be `domain`, `action`, `data_type`, `user_population`,
`platform`, `integration_method`, `support`, or `enforcement_history`.

### Candidate Risk Summary

One reviewable summary per candidate. Arrays remain multi-valued:

```text
opportunity_id
regulated_domain_tags
regulated_action_tags
decision_criticality
consequence_of_error_signal
requested_sensitive_data_tags
inferred_sensitive_data_tags
vulnerable_user_tags
third_party_dependencies
core_dependency_count
distribution_platform_tags
platform_policy_trigger_tags
declaration_required_tags
license_clearance_registration_tags
privacy_request_obligation_tags
scraping_or_api_dependency_tags
support_burden_tags
regulatory_sensitivity_signal
privacy_risk_signal
platform_dependency_signal
support_burden_signal
explicit_prohibition_present
license_or_clearance_required
legal_entity_required
disqualifying_condition_flag
human_review_required
manual_legal_review_recommended
risk_tags
risk_evidence_count
supporting_risk_claim_ids
missing_inputs
```

`disqualifying_condition_flag` preserves language from supplied ideal guidance,
but means “inspect explicit potential hard stop,” not “discard candidate.”

### Dependency Record

One row per external platform or API:

```text
dependency_id
opportunity_id
dependency_name
core_or_optional
official_api_exists
api_required
access_mode
authentication_required
default_quota
rate_limit_known
rate_limit_value
paid_api
commercial_use_restrictions
data_retention_restrictions
redistribution_restrictions
api_termination_right
api_change_right
terms_url
api_docs_url
retrieved_at
raw_evidence_ids
```

### Authority Source Registry

Maintain a small local registry mapping triggers to likely authority families.
Each entry needs:

```text
authority_source_id
trigger_tags
publisher
source_type
jurisdiction_or_platform
canonical_url
known_reference
retrieval_priority
last_verified_at
content_hash
prior_version_artifact_ids
notes
```

The practical assessment suggests 20–40 carefully selected documents could
cover much early scope. Treat that range as a starting hypothesis, not a quota.

## Evidence Source Hierarchy

Use source type to order manual review:

1. `OFFICIAL_REGULATOR`
2. `OFFICIAL_PLATFORM_POLICY`
3. `OFFICIAL_MARKETPLACE_GUIDE`
4. `STATUTE_CASE_OR_COURT_RECORD`
5. `QUALIFIED_LEGAL_ANALYSIS`
6. `OPERATOR_MATERIAL`
7. `COMMUNITY_DISCUSSION`

Hierarchy expresses usual authority and stability. It does not make a source
applicable, current, complete, or correctly interpreted. Capture conflicting
sources and dates rather than silently selecting one.

## Classification and Derived Signals

### Classification Order

1. Exact deterministic phrase or field match.
2. Curated synonym and pattern rules.
3. Product-surface and workflow context.
4. Known trigger-to-authority mapping.
5. Optional semantic similarity or local model.
6. Optional LLM classification with preserved input, output, rule version, and
   supporting IDs.
7. Human review for ambiguity or consequence-heavy claims.

spaCy, `sentence-transformers`, or a local model through Ollama are possible
future helpers. They are not MVP requirements and their output never becomes
authority evidence.

### Separate Component Signals

Use `LOW`, `MEDIUM`, `HIGH`, or `UNKNOWN` for:

- regulatory sensitivity;
- consequence of error;
- privacy risk;
- platform dependency;
- support burden.

Suggested deterministic framing:

- **Regulatory sensitivity:** High when regulated domain combines with
  individualized diagnosis, treatment, advice, filing, legal discretion,
  authorization, clearance, registration, or legal-entity evidence. Medium for
  mainly informational regulated-domain use. Unknown when function is unclear.
- **Consequence of error:** High for plausible physical harm, dosage, diagnosis,
  crisis response, loss of legal rights, official filing, or material financial
  loss. Keep independent of rule applicability.
- **Privacy risk:** High when sensitive/inferred data or minors combine with
  sharing, tracking, syncing, third-party SDKs, weak predictability, or weak
  manageability. Medium when sensitive data appears limited to core function.
- **Platform dependency:** High when one external platform or API is essential
  and review, policy, rate limits, revocation, or terms can interrupt core use.
- **Support burden:** High when moderation, child safety, urgent correction,
  privacy requests, incident handling, or prompt marketplace support is
  required. Integration or onboarding complexity without constant moderation
  may be medium.

Any optional overall label must be a transparent summary of these components,
must preserve `UNKNOWN`, and must never drive ranking or rejection.

### Hard-Stop Flags

Allowed labels:

```text
EXPLICIT_PROHIBITION_PRESENT
LICENSE_OR_CLEARANCE_REQUIRED
LEGAL_ENTITY_REQUIRED
HUMAN_REVIEW_REQUIRED
MANUAL_LEGAL_REVIEW_RECOMMENDED
```

Set an explicit-prohibition flag only when source language directly says the
behavior is not allowed. Set authorization or entity flags only when an official
source identifies a relevant requirement. Preserve applicability uncertainty.
All hard-stop flags route to manual review.

## False Positives to Prevent

- Topic mention mistaken for regulated action.
- General health data mistaken for automatic HIPAA applicability.
- Adult or mixed-audience product mistaken for child-directed use solely because
  children might access it.
- Public data mistaken for legally risk-free scraping.
- High risk mistaken for explicit prohibition.
- General educational finance content mistaken for personalized investment
  advice.
- Tax calculation or education mistaken for official e-file transmission.
- Legal information mistaken for case-specific legal discretion.
- Marketplace policy match mistaken for predicted rejection.
- Missing authority evidence mistaken for low risk.

## False Negatives to Prevent

- Sensitive status inferred from workflow but never explicitly requested.
- Third-party analytics, tracking pixels, advertising SDKs, or identity linkage
  omitted from privacy review.
- Moderation, child-safety, deletion, privacy-request, or support duties hidden
  inside marketplace rules.
- Legal-entity, registration, authorization, documentation, or declaration
  requirements omitted because product appears technically simple.
- Optional feature introducing most risk left unseparated from core job.
- Platform dependency omitted because public access works today.
- Policy version changes erased by overwriting prior captures.
- Complaint or issue counts copied without their raw records and sample bounds.

## Practical Source Strategy

All availability, quota, cost, and policy statements below are user-supplied
planning notes received 2026-08-15. They are not independently verified. Recheck
official documentation and terms before implementation or collection.

### First Release: Local and Curated

1. **Deterministic local rules:** Primary detector for domains, functions,
   sensitive data, vulnerable users, consequence of error, support complexity,
   and dependencies. Near-zero marginal collection cost.
2. **Curated authority registry:** Trigger-based mapping to a small set of FDA,
   HHS, FTC, SEC, FINRA, IRS, Apple, Google, Chrome, Slack, Shopify, Atlassian,
   and other directly relevant materials.
3. **Direct HTTP retrieval:** Use known canonical URLs instead of repeated search.
   Preserve page title, publisher, canonical URL, retrieval time, relevant text,
   content hash, and change history. Static parsers are preferred; Playwright is
   optional for necessary JavaScript-rendered pages.
4. **Apple App Review and privacy policy:** Match iOS surfaces, regulated fields,
   health, children, UGC, payments, privacy, SDK responsibility, support, and
   public-API rules.
5. **Google Play policy:** Match health and financial declarations, medical
   proof/disclaimer conditions, User Data, Families, UGC, SDK, monetization,
   account deletion, and support requirements.
6. **Static IRS mapping:** Distinguish tax education/calculation from actual
   return preparation or e-file transmission. Do not parse every tax rule.

### Conditional First-Release Enrichment

7. **Web discovery:** Choose one provider after verification rather than
   integrating several. Supplied options:
   - Brave Search: claimed $5 per 1,000 searches with recurring $5 monthly
     credit, enough for roughly 1,000 basic searches/month.
   - Tavily: claimed 1,000 free credits/month; basic search one credit, advanced
     search two, and basic extraction one credit per five successful URLs.
   - Google Programmable Search: supplied claim of $5 per 1,000 queries and
     10,000 JSON queries/day, but no preferred role. Availability is especially
     unstable and must be reverified.
   Use roughly two to five searches only after a trigger fires. Search results
   discover sources; underlying pages support claims.
8. **Federal Register API:** Supplied as free with no API key. Use for proposed
   rules, final rules, notices, agency metadata, dates, and CFR references after
   a domain trigger. Example discovery phrases from supplied planning material
   include `mobile medical applications`, `health app privacy`, `online
   investment adviser`, `children online privacy`, and `artificial intelligence
   medical`. It is enrichment, not primary classification.
9. **openFDA:** Use only behind medical-device triggers for device
   classifications, 510(k)s, PMAs, labels, adverse events, or recalls relevant to
   the question. Supplied limits: 1,000 requests/day without a key and 120,000
   with a free key. Similar records describe evidence; they do not classify the
   candidate.
10. **GitHub API:** Use only when open-source platform or integration issues are
    relevant. Supplied limits: 60 unauthenticated and 5,000 authenticated
    requests/hour. Potential fields include open issues, recent bugs,
    integration breakage, authentication failures, and rate-limit failures.
11. **Platform/API documentation and terms:** Retrieve only for named core
    dependencies. Capture official API existence, quotas, audits, restrictions,
    retention, redistribution, revocation, and change rights.

### Secondary or v1.5

- **eCFR API:** Official machine-readable current regulations. Use known family
  and known CFR reference after classification, not semantic search over all CFR
  text. Direct FTC/FDA/HHS guidance may be more readable for v1.
- **Regulations.gov API:** Supplied as full-text rulemaking access using a free
  `api.data.gov` key. Useful later for dockets, comments, active rulemaking,
  agencies, activity counts, and latest dates.
- **CFPB Consumer Complaint Database:** Free API/download according to supplied
  notes. Potentially useful for financial complaint volumes, product/issue
  categories, recent counts, and available narratives. Also relevant to problem
  and competitor clusters; preserve ownership and cross-cluster IDs.
- **API terms extraction and robots:** Capture exact terms matches and technical
  status. Add automated extraction only when it remains reviewable.
- **Enforcement discovery:** Search official FTC, SEC, FDA, or other authority
  sites for cases, then manually or traceably classify analogy. Defer broad
  similarity claims.

### Not an MVP Dependency

- **GovInfo:** Free `api.data.gov` key according to supplied notes, but redundant
  with Federal Register and eCFR for current needs.
- **FTC developer APIs:** FTC guidance and enforcement pages are valuable; the
  supplied assessment says available developer endpoints do not provide a
  general search API for all enforcement cases. Prefer direct official pages.
- **Official competitor review APIs:** Apple App Store Connect and Google Play
  Developer APIs primarily expose the authenticated developer's own apps. Reuse
  traceable review data already collected elsewhere.
- **Reddit API:** Terms, commercial-use, revocation, rate-limit, and retention
  restrictions make it a platform-risk example, not a required data source.

## Initial Curated Authority Families

These URLs came from supplied planning material. They are seed locations only;
verify canonical URL, current text, date, jurisdiction, and applicability before
creating evidence records.

- Apple App Review Guidelines:
  `https://developer.apple.com/app-store/review/guidelines/`
- Apple App Privacy Details:
  `https://developer.apple.com/app-store/app-privacy-details/`
- Google Play Health Content and Services:
  `https://support.google.com/googleplay/android-developer/answer/16679511`
- Google Play User Data:
  `https://support.google.com/googleplay/android-developer/answer/10144311`
- Google Play User Generated Content:
  `https://support.google.com/googleplay/android-developer/answer/9876937`
- FDA Device Software Functions and Mobile Medical Applications:
  `https://www.fda.gov/medical-devices/digital-health-center-excellence/device-software-functions-including-mobile-medical-applications`
- FTC Mobile Health Apps Interactive Tool:
  `https://www.ftc.gov/business-guidance/resources/mobile-health-apps-interactive-tool`
- FTC Health Breach Notification Rule guidance:
  `https://www.ftc.gov/business-guidance/resources/complying-ftcs-health-breach-notification-rule-0`
- FTC Premom enforcement material:
  `https://www.ftc.gov/news-events/news/press-releases/2023/05/ovulation-tracking-app-premom-will-be-barred-sharing-health-data-advertising-under-proposed-ftc`
- FTC BetterHelp enforcement material:
  `https://www.ftc.gov/news-events/news/press-releases/2023/07/ftc-gives-final-approval-order-banning-betterhelp-sharing-sensitive-health-data-advertising`
- FTC GoodRx enforcement material:
  `https://www.ftc.gov/news-events/news/press-releases/2023/02/ftc-enforcement-action-bar-goodrx-sharing-consumers-sensitive-health-info-advertising`
- HHS Covered Entities and Business Associates:
  `https://www.hhs.gov/hipaa/for-professionals/covered-entities/index.html`
- IRS authorized e-file provider guidance:
  `https://www.irs.gov/e-file-providers/become-an-authorized-e-file-provider`
- SEC robo-adviser guidance:
  `https://www.sec.gov/investment/im-guidance-2017-02.pdf`
- Chrome Web Store Limited Use policy:
  `https://developer.chrome.com/docs/webstore/program-policies/limited-use`
- Slack Marketplace review guide:
  `https://docs.slack.dev/slack-marketplace/slack-marketplace-review-guide`
- Slack Marketplace app guidelines and requirements:
  `https://docs.slack.dev/slack-marketplace/slack-marketplace-app-guidelines-and-requirements/`
- X Developer Policy:
  `https://docs.x.com/developer-terms/policy`
- ICO special-category data guidance:
  `https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/lawful-basis/special-category-data/what-is-special-category-data/`
- NIST Privacy Engineering IR 8062:
  `https://csrc.nist.gov/pubs/ir/8062/final`

Possible future authority families without fixed seed URLs yet include FINRA
digital investment advice, Shopify App Store rules, Atlassian Marketplace
privacy/security and approval requirements, state-bar legal-service rules, and
official child-directed product guidance. Discover and verify official sources
only when corresponding triggers fire.

## Evidence Preservation

Every claim must preserve both sides:

1. exact or bounded candidate-side text/observation suggesting the behavior;
2. exact or bounded authority-side excerpt explaining why it matters.

Authority packets should contain title, canonical URL, publisher/domain,
jurisdiction/platform, publication or last-updated date, retrieval time, source
type, excerpt, claim summary, evidence direction, confidence tier, content hash,
and prior snapshot reference when available.

Preserve complete raw responses before normalization when permitted. Stable IDs
must survive tagging, source matching, enrichment, summary, and profile output.
Every aggregate must name its denominator and supporting IDs. Policy changes
should create new artifacts rather than mutate old evidence.

Example compact human review form:

```text
Risk tag
Candidate trigger
Why it may matter
Component severity
Evidence direction
Authority excerpt and URL
Applicability unknowns
Manual review note
```

## Profile Guidance

The cluster primarily populates section 8, Risk and Regulation Evidence, but a
risk claim may reference evidence owned by another section. Do not duplicate or
relabel that source without stable IDs.

- Section 1 may identify harmful outcomes or recurring safety-sensitive jobs.
- Section 2 may show risky manual workarounds.
- Section 3 may contain support, privacy, billing, data-loss, or reliability
  complaints useful as operational indicators.
- Section 4 may show paid regulated services nearby, without proving the
  candidate can legally provide them.
- Section 5 may provide competitor platform surfaces, permissions, claims, and
  review evidence.
- Section 6 may locate authority sources but search snippets are discovery only.
- Section 7 may expose marketplace/community access and moderation constraints.
- Section 8 contains paired, evidence-backed risk claims and component signals.
- Section 9 indexes raw candidate triggers and authority artifacts.

## Confirmed Facts

- No market, candidate, legal-applicability, or risk facts have been collected
  yet. Supplied documents are planning context only.

## Hypotheses

- Local deterministic classification plus a small curated authority registry
  will cover most decision-useful MVP risk signals more cheaply and clearly than
  broad regulation search.
- Function and consequence-of-error tags will discriminate risk better than
  domain labels alone.
- Paired candidate/authority evidence will reduce vague legal alarmism and make
  manual review faster.
- Platform dependency and support obligations may expose practical blockers
  earlier than comprehensive legal research.
- Twenty to forty verified authority documents may cover a large share of early
  small-software candidates; coverage remains unmeasured.
- One general web discovery provider should be sufficient initially if direct
  retrieval handles known authoritative URLs.

## Open Questions

- What shared runner interface and cross-cluster evidence-reference contract
  will exist?
- What exact controlled vocabularies and versioning format should v1 use?
- Which 20–40 authority documents should form the first verified registry?
- Brave or Tavily: which provider has current acceptable pricing, terms,
  extraction quality, and retention conditions at implementation time?
- What candidate-side inputs will be available reliably: descriptions, source
  excerpts, feature hypotheses, competitor pages, permissions, SDKs, or API
  dependencies?
- What confidence threshold routes deterministic matches directly to review,
  and what ambiguity requires semantic classification?
- How should policy snapshots be versioned and deduplicated across retrievals?
- Which jurisdictions should be represented first beyond US federal and major
  marketplace policies?
- How will optional-feature boundaries be supplied or inferred without turning
  the cluster into a product-design recommender?

## Decisions and Superseded Guidance

- Current project boundary supersedes the ideal specification's suggestion that
  a high-confidence disqualifying flag could auto-drop an idea. This cluster
  never auto-drops, approves, ranks, or chooses; it surfaces explicit evidence
  for user review.
- Practical API assessment narrows the ideal broad ontology for MVP. Start with
  local classification, curated sources, direct retrieval, Apple/Google policy,
  static IRS mapping, and conditional Federal Register/openFDA/GitHub/search.
- Broad live regulation discovery is not the centerpiece. Enrichment follows a
  candidate trigger and known authority family.
- Deterministic rules precede semantic or LLM classification. Models may tag or
  summarize but cannot supply evidence or legal conclusions.
- Risk components remain separate. An optional overall signal is transparent
  triage metadata, never a single opportunity score.
- Official competitor-review APIs will not be treated as general competitor
  sources. Reuse existing evidence through stable cross-cluster IDs.
- State, international, HIPAA, medical-device, legal-practice, investment-
  adviser, licensing, scraping-legality, enforcement-probability, compliance-
  cost, support-hour, and store-acceptance determinations remain outside MVP.

## Context Change Log

- 2026-08-15: Created cluster context from supplied ideal specification and
  practical API-access assessment. Classified both as planning context, adopted
  evidence-first trigger-based MVP, and removed automatic rejection from scope.
