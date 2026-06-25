# Methodology Notes

This document summarizes the analytical methodology behind the project.

## 1. Objective

The project aimed to identify visual characteristics associated with higher or lower performance in digital advertising creatives for spirits campaigns.

The analysis was exploratory and associative, not causal.

## 2. Data Sources

- Campaign performance data: impressions, clicks, CTR, campaign metadata, country, dates.
- Skai API enrichment: image URLs and creative metadata linked by ad identifier.
- AI visual classification: structured variables generated from creative image URLs.

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

## 4. Related Repositories

- [bigquery-skill](https://github.com/anabelengarciac/bigquery-skill): warehouse exploration and query validation.
- [spirits-creative-image-enrichment](https://github.com/anabelengarciac/spirits-creative-image-enrichment): image URL enrichment from Skai.
- [spirits-creative-performance-ai](https://github.com/anabelengarciac/spirits-creative-performance-ai): Skai performance export and quality-check workflow.

## 5. Interpretation

The results should be read as exploratory evidence. CTR was used as an operational performance metric, but creative effectiveness may also depend on brand equity, audience, placement, budget, frequency, campaign objective, and market context.
