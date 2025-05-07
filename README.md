# Email Marketing Experiment for Funding Rate Improvement

## Background & Motivation

A fintech company aims to increase key user actions—account linking, funding, and trading—by sending targeted email campaigns. This project segments users, tests email templates, and optimizes delivery order and frequency to drive funding behavior.

## Hypothesis

1. Email outreach is the most effective channel for re-engaging approved yet unfunded users.
2. User behavior (open rate, funding rate) is influenced by:

   * **User segment** (approval age, bank linkage, recent activity)
   * **Email content** (subject line, GIF, copy)
   * **Message sequence**
   * **Delivery frequency**

## Audience

* 480,000 unfunded users
* Two-week observation window after email delivery completes

## Goals

* **Primary:** Increase email open rate and funding rate
* **Secondary:** Validate differences across user segments and email schedules

## Metrics

* **Engagement:** Open rate, click-through rate, app opens
* **Activation:** Link rate, first funding, 1+ trades, 2+ trades
* **A/B Test:** ΔFunding rate vs. control

## Experiment Design

1. **Email Templates:** 10 categories covering trust, knowledge, and usability
2. **User Segments:** 12 cohorts (approved<6mo, bank linked, recent trades, etc.)
3. **Delivery Frequencies:** Daily (`*_D`) vs. twice-weekly (`*_W`)
4. **Randomized Order:** Each user receives a random permutation of the 10 emails
5. **Timeline:** Day 0 through Day 32; +2 weeks post-send for final metrics

## Data Files

* `Sample_segment_groups.csv`: User segment definitions (12 groups)
* `Sample_uuid_email_order.csv`: Email schedule and template indices per user
* `user_events.csv`: User status (link, fund, trading) and email delivery flags
* `control_groups_rate.csv`: Control group link/funding summary
* Optional: `email_events.csv` for raw email interactions

> **Note:** PO\_number\_list defines template IDs:
>
> ```python
> PO_number_list = [
>   'ml_funding_enables_investing', 'ml_investing_starts_here',
>   'ml_explore_the_app_investing', 'ml_funding_faq',
>   'ml_user_clustering_emails_fracs', 'ml_funding_is_safe',
>   'ml_picking_an_investment', 'ml_investing_101',
>   'ml_diversified_portfolio', 'ml_explore_the_app_list'
> ]
> ```

## Analysis Tasks

1. **Open Rate Analysis**
   a. Identify the best-performing email template
   b. Correlate open rate with user segment factors
   c. (Optional) Detect any negative effects (e.g., unsubscribes)

2. **Link & Funding Rates**

   * Compute link and funding rates for each treatment group

3. **A/B Testing**

   * Assess whether emails causally improve funding vs. control

4. **Time Series Insights**
   a. Does Day 0 maximize opens?
   b. Is the experiment window sufficient?

5. **Funnel Analysis (Optional)**

   * Visualize Link → Open → Fund across segments and overall
