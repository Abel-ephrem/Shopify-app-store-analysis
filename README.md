# Analyst Memo — Shopify App Store Insights

**Dashboard:** Shopify App Store Analysis
**Reporting Period:** Latest available data

## Key Insight

The marketplace is growing fast and merchants are generally satisfied, but satisfaction varies by category and developers rarely engage with reviews.

- 500 apps, 7,980 reviews, **4.19** average rating.
- Reviews grew from 262 (2020) to **3,804** (2024) while ratings held steady.
- Productivity (4.39) and Sales & Conversion (4.35) rate highest; Loyalty & Rewards (4.02) rates lowest.
- Only **24.8%** of reviews get a developer reply.

## Business Impact

- Low-rated categories signal unmet merchant needs and possible churn.
- Under-reviewed categories (e.g. Inventory Management, about 8 reviews per app) give merchants less evidence to choose with.
- Rankings based on raw averages would promote apps with very few reviews.

## Recommendation

1. Investigate Loyalty & Rewards and Subscriptions for common merchant pain points.
2. Encourage reviews in under-reviewed categories.
3. Apply a 20-review minimum to any "top apps" ranking.
4. Promote developer replies and track Developer Reply % over time.

---

## For Analysts

**Files:** `ShopifyAppAnalysis.pbix`, `overview_page.png`, `trend_analysis_page.png`, `model_view.png`

**Data prep (Power Query):** removed duplicate `review_id`s, standardized mixed date formats (`MM/DD/YYYY` assumed), removed ratings outside 1 to 5, cleaned category names, filled missing developers and prices.

**Model:** `apps[app_id]` → `reviews[app_id]` and `dim_date[Date]` → `reviews[posted_at]` (both one-to-many). `dim_date` is the marked date table.

**Measures:** Total Apps, Total Reviews, Average Rating, Developer Reply %, App Rank, Reviews PY, YoY %, Prev Month, MoM %, YTD, YTD PY, MTD.

**Pages:** *Overview* (KPIs, slicers, review trend, rating by category, top 10 apps) and *Trend Analysis* (YoY, MoM and YTD comparisons). A page navigator links the two.

**Limitations:** no review text, so no sentiment analysis; findings are descriptive, not causal.
