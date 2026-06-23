# Strict recommendation re-extraction audit

This is a conservative replacement layer for the previous over-inclusive recommendation extraction.

## Decision

- Do not use `recommendation-extraction-reviews/subagent_by_guideline` as Delphi input.
- Use `included_strict` only for provisional synthesis.
- Read `needs_manual_read` rows against the source before inclusion.

## Counts

| Status | n |
|---|---:|
| included_strict | 474 |
| excluded_artifact | 105 |
| needs_manual_read | 22 |
| included_strict_unique | 403 |
| duplicate_repeated_statement | 71 |

## Top reasons

| Reason | n |
|---|---:|
| direct_recommendation_source_backed | 403 |
| already_excluded_in_verified_layer | 92 |
| duplicate_repeated_statement | 71 |
| too_long_probable_rationale | 10 |
| no_direct_clinical_action_detected | 9 |
| multi_statement_fragment | 6 |
| wrong_scope_or_wrong_topic | 2 |
| evidence_review_not_recommendation | 2 |
| artifact_like_section_heading | 2 |
| rationale_not_recommendation | 1 |
| methodology_or_disclaimer | 1 |
| research_agenda | 1 |
| low_source_overlap_0.22 | 1 |

## Included strict unique by theme

| Theme | n |
|---|---:|
| Clozapine for treatment-resistant schizophrenia | 44 |
| LAI/depot antipsychotics and adherence | 31 |
| CBTp and psychological therapies | 24 |
| Dose, titration and adequate trial duration | 23 |
| Family intervention and psychoeducation | 21 |
| Physical, metabolic and cardiovascular monitoring | 21 |
| First episode psychosis and early intervention | 20 |
| Diagnostic assessment, baseline workup and care planning | 19 |
| Antipsychotic choice and comparative selection | 17 |
| Acute agitation, rapid tranquillisation and crisis setting | 16 |
| Supported employment, education and vocational rehabilitation | 16 |
| Antipsychotic adverse-effect management | 14 |
| Social skills, recovery and self-management | 13 |
| Weight management, lifestyle and metformin | 12 |
| Maintenance treatment and relapse prevention | 11 |
| Depression, anxiety, PTSD and trauma | 11 |
| Clozapine safety and monitoring | 9 |
| Culture, equity, age and other special populations | 8 |
| Substance use comorbidity | 7 |
| Smoking cessation and tobacco | 7 |
| ACT, case management and community service models | 7 |
| Primary care transition, discharge and follow-up continuity | 7 |
| Acute antipsychotic initiation | 6 |
| Negative symptoms | 6 |
| Pregnancy, reproductive and perinatal care | 6 |
| Shared decision-making and patient preferences | 5 |
| At-risk mental state and prevention of psychosis | 4 |
| Cognitive remediation, metacognitive and social cognition training | 4 |
| Arts, mindfulness, digital and adjunctive psychosocial interventions | 4 |
| ECT and other biological treatments | 3 |

## Included strict unique by guide

| Guide | n |
|---|---:|
| G01_2014_d279bd | 23 |
| G02_2014_fe8069 | 81 |
| G03_2014_c8c7f4 | 6 |
| G04_2016_9b6bb7 | 25 |
| G05_2016_09a4fc | 11 |
| G06_2017_7218de | 14 |
| G07_2017_05765f | 8 |
| G08_2017_67bbf9 | 7 |
| G09_2017_112ab5 | 11 |
| G10_2019_f4f8de | 16 |
| G11_2020_0be63e | 34 |
| G12_2020_25e9c9 | 49 |
| G13_2024_32035c | 5 |
| G14_2024_612bb3 | 37 |
| G15_2024_ecacbb | 17 |
| G17_2025_dc22c0 | 28 |
| G18_2026_972935 | 27 |
| G19_2026_32004f | 4 |

## Known failure modes fixed

- Evidence-review bullets such as `Directness:` are excluded.
- Research-agenda rows are excluded.
- Methodology/disclaimer rows are excluded.
- Wrong-scope comorbidity fragments such as antiobsessive/SSRI text are excluded.
- Mindfulness/ACT/EMDR recommendations are assigned to the adjunctive psychosocial theme instead of discontinuation.
- Repeated guideline statements are deduplicated before matrix/count generation.
