# SUBMISSION.md

## What this analysis is trying to do

The focus here is not on ranking features, but on identifying directions that are less likely to be regretted under uncertainty.

While the dataset provides some useful signals, it is also quite noisy. The extracted nonsafety labels include a mix of genuine customer-driven demand, Voxel-led problem framing, recurring operational friction, and bespoke requests. The goal is not to count which topics appear most frequently. The goal is to identify the signals that are strongest in terms of reusability, credibility, and priority for further validation.


My decision lens: **reusability**, **customer evidence quality**, **boundary clarity**, **next-step fitness**.

---

## Dataset and evidence boundary

I analyzed **99 anonymized call JSON files** covering **231 nonsafety use cases**.

Evidence is split into three aspects:

- **Hard**: it directly comes from JSON fields.
- **Proxy**: It comes from the JSON data, but its interpretation depends on clearly stated assumptions.
- **Soft**: it requires subjective judgment and is not used as primary evidence.

---

## Analysis logic

This analysis treats the original nonsafety labels as noisy raw inputs.
From the very beginning of data processing, the results show a high level of fragmentation, with 228 unique labels observed in 231 cases.

Here are the logic flows in three stages:

**Quality checks first.** 
To distinguish more clearly customer-driven needs from Voxel-led discussions, each case is first classified based on speaker origin. Thus, the cases are categorized as customer_only, mixed, or voxel_only.
Next, at the same time, a check was conducted to see whether there are any exact label overlaps between the safety and nonsafety categories. 
This is intended to check how clearly the categories are separated.

**Normalization second.** 
The presence of 228 labels does not imply 228 opportunities. 
Considering this, we do not treat the label count alone as a reliable measure of opportunity. 
To improve interpretability, we map the labels to six reusable primitives and then group them into higher-level themes.
Notably, this is the core of the entire analysis.
This step makes it possible to consolidate surface-level variations in wording into representations that better reflect the underlying capabilities.


**Judgment layer last.** 
The first step is to evaluate all themes using a set of five hard metrics and one proxy, with attention to coverage, customer evidence quality, evidence depth, boundary risk across categories, and coverage across domains.
On top of this, I classify each theme by determining whether it is closer to validate now, real but unresolved, existing-motion echo, or noise/bespoke.

Once the themes had been classified, I also introduced a time-based analysis, including a look at how speaker composition differs by year. 
This step is mainly used as supporting analysis. 

---

## Files

| File | What it is |
|---|---|
| `memo.md` 
| `submission.md`
| `voxel_takehome.ipynb` | Notebook with full step-by-step analysis and visualizations |
