# Data Engineering Interview Questions

> A 2026 question bank for data engineering interviews. Organized by topic. Every question links to a runnable browser sandbox.

[![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC_BY--SA_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by-sa/4.0/)
[![Last updated](https://img.shields.io/badge/updated-2026-blue.svg)](#)

## Why a 2026 edition

The most popular DE interview question repos on GitHub were written in 2018 to 2021. They predate dbt going mainstream, predate Iceberg and Delta, predate the lakehouse pattern, predate the streaming default, and predate the current generation of system design rounds. They are still useful for fundamentals, but they will not prepare you for a 2026 onsite at Netflix, Stripe, Databricks, or Snowflake.

This bank is current. Every question reflects the way these topics are actually being asked in 2026 loops. Each question links to a sandbox where you can run the schema and submit your answer.

## How this is organized

Five sections, one per round:

1. **SQL** (854 questions). What you will see in screens and onsites.
2. **Python** (388 questions). DE flavored, not LeetCode.
3. **Schema design** (56 questions). Whiteboard ERDs.
4. **Pipeline architecture** (120 questions). End to end design.
5. **Behavioral** (50 questions). Story bank prompts.

Each question is tagged with:

- **Difficulty.** Easy, medium, hard.
- **What it tests.** The underlying skill.
- **Common trap.** The mistake that costs candidates the offer.
- **Sandbox link.** A runnable environment with the schema preloaded.

## SQL questions

The full SQL set with filters by difficulty and topic is browseable at <https://datadriven.io/sql-interview-questions>.

### Top 25 SQL questions to know cold

| # | Question | Difficulty | Tests | Common trap |
|---|---|---|---|---|
| 1 | [10 Lowest Uptime Services](https://datadriven.io/interview/10_lowest_uptime_services) | Easy | TOP N with ties | Using `LIMIT 10` and silently dropping ties |
| 2 | [2FA Confirmation Rate](https://datadriven.io/interview/2fa_confirmation_rate) | Easy | Conditional aggregation | Dividing by zero |
| 3 | [2nd Most Common Content Type](https://datadriven.io/interview/2nd_most_common_content_type) | Easy | Tie breaking | `LIMIT 1 OFFSET 1` ignoring ties at first place |
| 4 | [30 Day Page View Counts](https://datadriven.io/interview/30_day_page_view_counts) | Easy | Date filtering | Timezone boundary errors |
| 5 | [7 Day Onboarding Conversion](https://datadriven.io/interview/7_day_onboarding_conversion) | Medium | Funnel analysis | Anchoring on the wrong event |
| 6 | [7 Check Rolling Average](https://datadriven.io/interview/7_check_rolling_average) | Medium | Rolling window | `ROWS` vs `RANGE` when days are missing |
| 7 | [Active Users by Month](https://datadriven.io/interview/active_users_by_month) | Medium | Cohort logic | Double counting users active in multiple months |

The full top 100 list is at <https://datadriven.io/sql-interview-questions>.

### SQL questions by topic

- **[Window functions](https://datadriven.io/sql-window-functions-practice)**. The single highest leverage SQL topic. Every senior loop has at least one.
- **[Joins](https://datadriven.io/learn/joins-advanced)**. Inner, left, full, semi, anti, lateral, inequality.
- **[Aggregating](https://datadriven.io/learn/aggregating-advanced)**. `GROUP BY`, grouping sets, rollups, conditional aggregation.
- **[Date and time](https://datadriven.io/sql-tutorial)**. Almost every interview has a "compute by week" question with a hidden timezone trap.
- **[Performance reasoning](https://datadriven.io/sql-query-optimization)**. EXPLAIN plans, partitioning, sort keys.

### What SQL questions actually test

Senior DE SQL screens are not really about SQL. They test four things:

1. **Reflexes.** Can you write `LAG` from memory? Can you write a self join without thinking?
2. **Reading queries.** Can you find the bug in a query someone else wrote?
3. **Tradeoffs.** When would you use a CTE vs a subquery vs a temp table?
4. **Data quality.** When you see a question, can you spot when it is secretly a data quality problem?

If you have any one of these gaps, work it directly. The lessons at <https://datadriven.io/learn> are organized to do exactly that.

## Python questions

The full Python set is at <https://datadriven.io/python-interview-questions>.

### Top 15 Python questions to know cold

| # | Question | Difficulty | Pattern |
|---|---|---|---|
| 1 | [Batch Records](https://datadriven.io/interview/batch_records) | Easy | Chunking iterables |
| 2 | [Column Sum](https://datadriven.io/interview/column_sum) | Easy | Dict aggregation |
| 3 | [Activity Time Ledger](https://datadriven.io/interview/activity_time_ledger) | Medium | Interval merging |
| 4 | [Batch Partitioner](https://datadriven.io/interview/batch_partitioner) | Medium | Hash bucketing |
| 5 | [Batch With Metadata](https://datadriven.io/interview/batch_with_metadata) | Medium | Stateful iteration |
| 6 | [Caesar Shift Check](https://datadriven.io/interview/caesar_shift_check) | Hard | String transforms |
| 7 | [Character Occurrence Map](https://datadriven.io/interview/character_occurrence_map) | Hard | Counting tradeoffs |

### Python patterns to know

DE Python interviews almost never ask LeetCode style algorithms. They ask patterns. Memorize these:

1. **Chunking.** Split an iterable into batches of N.
2. **Hash partitioning.** Bucket records by `hash(key) % N`.
3. **Interval merging.** Merge overlapping time ranges.
4. **Sessionization.** Group events into sessions based on inactivity gap.
5. **Dedup with tie breaking.** First seen, last seen, or by priority.
6. **Streaming aggregation.** Maintain running counts in a single pass.
7. **Retries with backoff.** Common in API integration questions.
8. **Schema evolution.** Add a new field to a record stream without breaking consumers.

A walkthrough of each pattern with code lives at <https://datadriven.io/python-for-data-engineering>.

## Schema design questions

The full schema design set (56 problems with worked solutions) is at <https://datadriven.io/data-modeling-interview-questions>.

### Top 15 schema design questions

| # | Question | Tests |
|---|---|---|
| 1 | [A/B Experiment Assignment Schema](https://datadriven.io/interview/a_b_experiment_assignment_schema) | SCD type 2, sticky bucketing |
| 2 | [Customer Address History](https://datadriven.io/interview/customer_address_history) | SCD type 2, effective date semantics |
| 3 | [Insurance Claims Lifecycle](https://datadriven.io/interview/insurance_claims_lifecycle) | State machine modeling |
| 4 | [Clickstream and Session Schema](https://datadriven.io/interview/clickstream_and_session_schema) | Sessionization, late events |
| 5 | [E Commerce Supply Chain Tracking](https://datadriven.io/interview/e_commerce_supply_chain_tracking) | Multi entity tracking |
| 6 | [Loan Management Schema](https://datadriven.io/interview/loan_management_schema) | Bridge tables, party roles |
| 7 | [Cloud File Storage Metadata Schema](https://datadriven.io/interview/cloud_file_storage_metadata_schema) | Recursive hierarchies |
| 8 | [Financial Trading Warehouse](https://datadriven.io/interview/financial_trading_warehouse) | Time series, late arriving facts |
| 9 | [Content Engagement Data Model](https://datadriven.io/interview/content_engagement_data_model) | Fact table grain |
| 10 | [B2B Invoicing Data Model](https://datadriven.io/interview/b2b_invoicing_data_model) | Many to many with attributes |
| 11 | [Event Ticketing System Data Model](https://datadriven.io/interview/event_ticketing_system_data_model) | Inventory, reservations |
| 12 | [Edtech Classroom Engagement Schema](https://datadriven.io/interview/edtech_classroom_engagement_schema) | Hierarchical dimensions |
| 13 | [Fitness Studio Membership Schema](https://datadriven.io/interview/fitness_studio_membership_schema) | Subscription state |
| 14 | [Housing Marketplace Analytics](https://datadriven.io/interview/housing_marketplace_analytics) | Two sided marketplace |
| 15 | [Livestream Analytics Schema](https://datadriven.io/interview/livestream_analytics_schema) | Real time fact rollups |

### Schema design rubric

What interviewers are scoring on, in order:

1. **Did you ask about the read pattern?** Schemas exist to serve queries. If you do not know the query, you cannot design the schema.
2. **Did you pick the right grain for fact tables?**
3. **Did you handle history correctly?** SCD type 1, 2, or 6, and you can defend the choice.
4. **Did you talk about indexes and partitioning?** Even if not asked.
5. **Did you sketch sample queries?** This is the single fastest way to validate a schema.

A longer treatment of the rubric is at <https://datadriven.io/data-modeling>.

## Pipeline architecture questions

The full set of 120 case studies is at <https://datadriven.io/data-pipeline-interview-questions>.

### Top 12 pipeline questions

| # | Question | Domain |
|---|---|---|
| 1 | [Card Transaction Streaming Pipeline](https://datadriven.io/interview/card_transaction_streaming_pipeline) | Real time, exactly once |
| 2 | [Cellular Connectivity and App Log Data Warehouse](https://datadriven.io/interview/cellular_connectivity_and_app_log_data_warehouse) | High cardinality |
| 3 | [AWS Pipeline Auto Scaling for Variable Volume](https://datadriven.io/interview/aws_pipeline_auto_scaling_for_variable_volume) | Cost optimization |
| 4 | [Connected Vehicle Telemetry Pipeline](https://datadriven.io/interview/connected_vehicle_telemetry_pipeline_with_iac_deployment) | High volume IoT |
| 5 | [Capital Markets Intraday Risk Pipeline](https://datadriven.io/interview/capital_markets_intraday_risk_pipeline_with_bcbs_239_lineage) | Regulatory lineage |
| 6 | [Database Replication and Schema Normalization Pipeline](https://datadriven.io/interview/database_replication_and_schema_normalization_pipeline) | CDC |
| 7 | [Clickstream Pipeline for Apple Product Analytics](https://datadriven.io/interview/clickstream_pipeline_for_apple_product_analytics) | Event ingestion |
| 8 | [Cost Optimized Clickstream Data Lake](https://datadriven.io/interview/cost_optimized_clickstream_data_lake) | Storage tradeoffs |
| 9 | [Databricks Pipeline with Spark Performance Optimization](https://datadriven.io/interview/databricks_pipeline_with_spark_performance_optimization) | Spark internals |
| 10 | [E Commerce Platform Analytics Pipeline](https://datadriven.io/interview/e_commerce_platform_analytics_pipeline_orders_to_warehouse) | Orders to warehouse |
| 11 | [Event Driven Insurance Pipeline](https://datadriven.io/interview/event_driven_insurance_pipeline_with_async_claim_processing) | Async processing |
| 12 | [Document Ingestion and Text Extraction Pipeline](https://datadriven.io/interview/document_ingestion_and_text_extraction_pipeline) | Unstructured data |

### Pipeline design framework

Use this framework on every pipeline question:

1. **Clarify.** Volume per second, latency target, freshness tolerance.
2. **Pick batch vs stream.** Justify with the numbers from step 1.
3. **Pick storage.** Lake, warehouse, lakehouse, OLAP store, kv store.
4. **Sketch topology.** Source, ingest, transform, serve.
5. **Failure modes.** Backfills, replays, late data, dedup, schema evolution.
6. **Cost and operations.** Steady state spend, on call burden.

A long form treatment is at <https://datadriven.io/data-engineering-system-design>.

## Behavioral questions

The full set of 50 questions with model answers is at <https://datadriven.io/behavioral-interview-questions>.

The themes you should have stories for:

1. Owned an ambiguous problem end to end
2. Disagreed with a stakeholder and changed their mind
3. Broke production and recovered
4. Mentored someone or raised the team bar
5. Killed a project that was not worth doing
6. Shipped fast then cleaned up
7. Worked across teams or with non technical stakeholders
8. Made a tradeoff between scope, quality, and time

## Company specific questions

DE loops differ by company. Each guide includes loop structure, leveling, and a curated subset of questions from this bank that map to that company's style.

| Company | Guide |
|---|---|
| Netflix | <https://datadriven.io/companies/netflix/interview> |
| Uber | <https://datadriven.io/companies/uber/interview> |
| Amazon | <https://datadriven.io/companies/amazon/interview> |
| Google | <https://datadriven.io/companies/google/interview> |
| Meta | <https://datadriven.io/companies/meta/interview> |

## Difficulty distribution

| Section | Easy | Medium | Hard | Total |
|---|---|---|---|---|
| SQL | ~340 | ~390 | ~120 | 854 |
| Python | ~150 | ~180 | ~60 | 388 |
| Schema design | ~10 | ~30 | ~16 | 56 |
| Pipeline architecture | ~20 | ~70 | ~30 | 120 |

If you finish 100 medium and 25 hard problems across the four sections, you are ready for any senior DE loop.

## Contributing

If you have a question that should be in this bank, open an issue with:

1. The question text
2. The schema or input data
3. The expected output
4. What it tests
5. The common trap

The question will be reviewed and added to the bank with attribution.

## License

CC BY-SA 4.0. Question environments are hosted at <https://datadriven.io>.
