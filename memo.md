# Voxel Nonsafety Opportunities — Analyst Memo

## Bottom line up front

These 231 non-safety use cases should not be interpreted as 231 separate product opportunities.
They are a noisy but useful commercial signal information. Once normalized and pressure-tested, they support one main conclusion:

> **Flow & Throughput are the top priorities to validate right now, and they come with the lowest cost.
Security & Evidence appear to address a real market need, but it is still unclear whether they are worth prioritizing.
Action & Distribution are important, but they are more of an extension of existing directions rather than a new growth area.**

---

## Three structural problems in the extraction output

Before any opportunity analysis, three data quality issues need to be named explicitly.

**Label explosion.** 
There are 228 unique labels across 231 nonsafety cases (98.7% uniqueness). 
This pipeline is pretty good at staying close to what customers actually said, but it doesn’t do much to group similar ideas up into reusable categories.
Therefore, simply counting how often a raw label appears does not reliably reflect the true strength of the demand.

**Mixed evidence origin.** 
Of 231 cases, 74 are supported only by Voxel speakers (32.0%), 77 are customer-only (33.3%), and 80 are mixed (34.6%).
 A third of the extraction output cannot be treated as customer pull without further review.

**Bucket instability.** 
28 labels appear in both safety and nonsafety buckets (exact match). 
The category boundaries have not yet fully stabilized, and this issue is especially important for themes that are closer to the core product.

---

## Opportunity scorecard

Because the raw labels are too scattered, analyzing them directly can get messy.
So I first merged them into six more fundamental categories, and then grouped them further under a few broader themes.
Each theme is scored on five hard signals from the JSON, plus one proxy column.

| Theme | Cases | D-calls | D-domains† | Cust-only% | Any-cust% | Multi-ev% | Overlap% | Motion |
|---|---:|---:|---:|---:|---:|---:|---:|---|
| **Flow & throughput** | 37 | 27 | 17 | 27% | 68% | 84% | **8%** | **Validate now** |
| **Security & evidence** | 17 | 16 | 9 | **41%** | 71% | 71% | **18%** | **Real but unresolved** |
| **Action & distribution** | 40 | 33 | 21 | 25% | 65% | 95% | 18% | **Existing-motion echo** |
| Training & adoption | 16 | 12 | 10 | 38% | 75% | 100% | 6% | Noise / enablement |
| Custom CV / bespoke | 15 | 12 | 9 | 60% | 73% | 73% | 7% | Noise / bespoke |

*† Domain count is a proxy. One domain ≠ one confirmed account.*

---

## The three main directions

### 1. Flow & Throughput 

Flow & Throughput are not the strongest on any individual metric.
But overall, its combination is the most well-balanced.
On the one hand, it has a certain scale, with 37 cases and 27 distinct calls.
On the other hand, the customer evidence is also fairly strong, with 68% of cases having at least some customer evidence.
At the same time, its safety overlap is only 8%, the lowest among the candidate directions.

From a temporal perspective, the shift in speaker mix also tends to support this direction.
Customer participation increased significantly from 58% in 2022 to 75% in 2023, and remained elevated at 69% in 2024.
Given the small sample size of roughly 12 to 13 cases per year, the result should be treated with caution.
I would be more inclined to interpret this as directional support rather than a strong conclusion.


Representative customer-only evidence: *"How frequently are operators stopped because of congestion? Is there a way to tally something as simple as that?"* / *"We're working on alleviating some of the congestion that we have in the dry dock."*

**Recommended next step:**
We can start by validating this direction.
Without a clear engineering evaluation, it may be a bit early to start new development.


---

### 2. Security & Evidence 

If we look at the customer-only metric, Security & Evidence is the strongest among the directions at 41%, which makes it appear more like a real commercial need.
The problem is its overlap rate: 18% of its labels also appear in the safety bucket. 
That raises a strategic question that the dataset cannot answer: is this a genuinely adjacent motion, or is it a reframing of value already close to the core product?

There are a few unclear areas, but that doesn’t necessarily make this direction a bad one.
I think what this really points to is that there’s a more fundamental question that needs to be answered first.
The key question is whether this requires a new buyer motion, or if it can be addressed by repackaging existing capabilities before making any product commitments.


Representative customer-only evidence: *"No pedestrian zone. This could be used for safety or security."* / *"Nobody should be in the registers if you're not an employee."*

**Recommended next step:**
The positioning needs to be clarified before it earns a place on the roadmap.


---

### 3. Action & Distribution 

Looking at coverage, Action & Distribution comes out as the largest theme in the data.
It covers 40 cases across 33 distinct calls.
But the customer signal behind it isn’t very strong.
It ranks lowest in customer-origin signal among the three candidate directions.
Customer-only is 25%, and any-customer is 65%.

The consumption-layer primitives dominating this theme, workflow, reporting, export, are areas where Voxel appears to be shaping the conversation rather than responding to unprompted customer pull.

This makes Action & Distribution important for understanding current Go-To-Market conversations, but not the strongest foundation for a new adjacent bet.

**Recommended next step:**  I would treat it as part of the existing direction, rather than a new expansion.

---

## Workflow improvement

Instead of reviewing all 231 nonsafety cases at the raw-label level, prioritize cases flagged by at least one of three mechanical rules:

- **voxel_only_hypothesis**: all evidence from @voxelai.com speakers → 74 cases (32.0%)
- **safety_overlap**: exact label match in safety bucket → 28 cases (12.1%)
- **exact_duplicate_label**: same label string appears more than once → 6 cases (2.6%)

The union of these flags covers **93 of 231 cases (40.3%)**. These rules require no model — only JSON field checks.

The more important shift, however, is not the flagging itself. It is reviewing at the **primitive / cluster level** rather than the raw-label level. That is how label explosion is addressed: by assessing cases as grouped capabilities, not as 228 individual phrases.

