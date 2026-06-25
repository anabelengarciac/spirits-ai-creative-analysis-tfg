# Conclusions

## Main Conclusion

The central contribution of this project is the possibility of **automating and reproducing the creative-performance analysis process**.

The project does not only analyze a specific set of spirits advertising creatives. It also proposes a workflow that can be repeated with new campaign periods, countries, brands, or datasets.

## 1. Automation As The Main Contribution

The analysis was designed as a pipeline rather than a manual review:

1. Extract performance data.
2. Enrich ads with creative image URLs.
3. Clean and validate the dataset.
4. Group ads by creative image.
5. Recalculate impressions, clicks, and CTR.
6. Segment creatives into Top and Low Performing groups.
7. Use AI to classify visual elements.
8. Compare patterns across groups and periods.

This structure makes the process easier to rerun, audit, and adapt.

## 2. Reproducibility

The workflow is reproducible because each step is explicit:

| Step | Reproducibility mechanism |
| --- | --- |
| Data extraction | BigQuery and Skai workflows are separated |
| Enrichment | `AdId -> ImageUrl` mapping is exported and auditable |
| Metric logic | CTR is recalculated from clicks and impressions after aggregation |
| Segmentation | Top and Low Performing groups follow defined rules |
| AI classification | Visual variables use structured categories |
| Validation | Aggregated metrics can be checked against source data |

This matters because creative analysis often depends on subjective judgement. A reproducible workflow makes the analysis easier to challenge, improve, and reuse.

## 3. AI As A Scaling Layer

AI was useful because it transformed images into structured variables. This allowed creative features to be compared quantitatively instead of reviewed only through manual interpretation.

Examples include:

- bottle presence,
- composition type,
- visual complexity,
- promotional overlays,
- logo visibility,
- call-to-action text,
- seasonal or premium visual codes.

The result is not a replacement for creative expertise. It is a way to scale the first layer of creative review and make it more systematic.

## 4. Practical Marketing Value

The method can help marketing teams:

- identify recurring creative patterns,
- compare top- and low-performing assets,
- review campaigns after key commercial periods,
- generate hypotheses for future creative testing,
- reduce dependence on purely subjective creative reviews.

The strongest business value is the ability to create a repeatable creative-learning loop.

## 5. Interpretation Limits

The results should be read as exploratory and associative.

CTR can indicate immediate interaction, but it does not capture every effect of advertising creativity. Creative effectiveness can also depend on audience, placement, frequency, budget, brand equity, campaign objective, and media context.

Therefore, the project should be understood as a methodology for structured creative learning, not as a causal model.

## Final Takeaway

The most valuable outcome is the workflow itself: a documented, repeatable system that connects campaign performance data, creative assets, AI visual classification, and business interpretation.
