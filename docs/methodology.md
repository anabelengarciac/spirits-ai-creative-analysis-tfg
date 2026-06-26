# Methodology Notes

This document summarizes the analytical methodology behind the project.

## 1. Objective

The project aimed to identify visual characteristics associated with higher or lower performance in digital advertising creatives for spirits campaigns.

The analysis was exploratory and associative, not causal.

The guiding question was:

> Are there visual patterns associated with advertising performance?

## 2. Data Sources

- Campaign performance data: impressions, clicks, CTR, campaign metadata, country, dates.
- Skai API enrichment: image URLs and creative metadata linked by ad identifier.
- AI visual classification: structured variables generated from creative image URLs.

The updated defense presentation makes the campaign scope explicit:

| Commercial period | Date window |
| --- | --- |
| Super Bowl | January 9 - February 9, 2025 |
| Black Friday + Cyber Monday | November 1 - November 30, 2025 |
| Christmas | December 1 - December 31, 2025 |

The main performance variables were impressions, clicks, and CTR. Skai was used to retrieve the creative URLs required for the visual analysis.

## 3. Processing Steps

1. Extract campaign performance data.
2. Identify the unique ad identifier.
3. Retrieve image URLs from Skai.
4. Join performance data and image metadata.
5. Remove rows without usable images.
6. Group repeated ads by image URL.
7. Recalculate impressions, clicks, and CTR at creative level.
8. Apply minimum impression thresholds.
9. Split creatives into Top and Low Performing groups.
10. Use AI to classify visual characteristics.
11. Compare visual patterns across groups and periods.
12. Validate aggregated metrics against the original source where possible.

## 4. AI Analysis Design

The AI analysis followed two iterations:

1. **Within-group analysis:** each performance group was analyzed separately to identify the most and least recurrent visual characteristics.
2. **Cross-group comparison:** the resulting analysis documents were compared to identify the clearest differences between Top Performing and Low Performing creatives.

This created a documented chain from raw campaign data to visual variables, then from visual variables to performance-group patterns.

## 5. Related Repositories

- [bigquery-skill](https://github.com/anabelengarciac/bigquery-skill): warehouse exploration and query validation.
- [spirits-creative-image-enrichment](https://github.com/anabelengarciac/spirits-creative-image-enrichment): image URL enrichment from Skai.
- [spirits-creative-performance-ai](https://github.com/anabelengarciac/spirits-creative-performance-ai): Skai performance export and quality-check workflow.

## 6. Interpretation

The results should be read as exploratory evidence. CTR was used as an operational performance metric, but creative effectiveness may also depend on brand equity, audience, placement, budget, frequency, campaign objective, and market context.

The updated presentation also highlights a practical limitation: the creative images available from the platform were catalog-style formats. This matters because the available image representation can influence which visual characteristics are observable.

## 7. Main Methodological Contribution

The most important methodological contribution is that the process can be automated and reproduced. Each stage is explicit enough to be rerun for another period, market, or campaign set:

- extract performance data,
- enrich with image URLs,
- clean and group at creative level,
- recalculate metrics,
- segment by performance,
- classify visuals with AI,
- compare patterns,
- document results.

This transforms creative analysis from a one-off manual review into a repeatable analytics workflow.
