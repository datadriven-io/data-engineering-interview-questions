<h1 align="center">Data Engineering Interview Questions</h1>

<p align="center">
  1418 tagged practice problems for data engineering interviews. SQL, Python, schema design, pipeline architecture. Each problem links to a runnable browser sandbox.
</p>

<p align="center">
  <a href="https://github.com/datadriven-io/data-engineering-interview-questions/stargazers"><img src="https://img.shields.io/github/stars/datadriven-io/data-engineering-interview-questions?style=flat&color=ffd33d" alt="Stars"></a>
  <a href="https://github.com/datadriven-io/data-engineering-interview-questions/blob/main/LICENSE"><img src="https://img.shields.io/badge/license-CC%20BY--SA%204.0-blue.svg" alt="License"></a>
  <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg" alt="PRs welcome">
  <a href="https://datadriven.io"><img src="https://img.shields.io/badge/sandbox-datadriven.io-9333ea.svg" alt="Sandbox"></a>
</p>

<p align="center">
  <a href="#sql-854-problems">SQL</a> ·
  <a href="#python-388-problems">Python</a> ·
  <a href="#schema-design-56-problems">Schema design</a> ·
  <a href="#pipeline-architecture-120-problems">Pipeline architecture</a> ·
  <a href="#companion-repos">Companion repos</a>
</p>

---

| Section | Count | Browse |
|---|---:|---|
| SQL | 854 | [datadriven.io/sql-interview-questions](https://datadriven.io/sql-interview-questions) |
| Python | 388 | [datadriven.io/python-interview-questions](https://datadriven.io/python-interview-questions) |
| Schema design | 56 | [datadriven.io/data-modeling-interview-questions](https://datadriven.io/data-modeling-interview-questions) |
| Pipeline architecture | 120 | [datadriven.io/data-pipeline-interview-questions](https://datadriven.io/data-pipeline-interview-questions) |
| **Total** | **1418** | |

Every problem runs in a browser sandbox with the schema preloaded. No local setup. Each question is tagged with difficulty, what it tests, and the common trap.

## SQL (854 problems)

Topics: joins, aggregating, window functions, filtering, dates, conditional aggregation, CTEs, performance reasoning. Topic browser at [datadriven.io/sql-interview-questions](https://datadriven.io/sql-interview-questions).

### Top problems to know cold

| Problem | Difficulty | Tests | Trap |
|---|---|---|---|
| [10 Lowest Uptime Services](https://datadriven.io/interview/10_lowest_uptime_services) | Easy | TOP N with ties | `LIMIT 10` drops tied rows |
| [2FA Confirmation Rate](https://datadriven.io/interview/2fa_confirmation_rate) | Easy | Conditional aggregation | Divide by zero |
| [2nd Most Common Content Type](https://datadriven.io/interview/2nd_most_common_content_type) | Easy | Tie breaking | `LIMIT 1 OFFSET 1` ignores ties |
| [30 Day Page View Counts](https://datadriven.io/interview/30_day_page_view_counts) | Easy | Date filtering | Timezone boundaries |
| [7 Day Onboarding Conversion](https://datadriven.io/interview/7_day_onboarding_conversion) | Medium | Funnel analysis | Anchoring on the wrong event |
| [7 Check Rolling Average](https://datadriven.io/interview/7_check_rolling_average) | Medium | Rolling window | `ROWS` vs `RANGE` when days are missing |
| [Active Users by Month](https://datadriven.io/interview/active_users_by_month) | Hard | Cohort logic | Double counting users active in multiple months |

### Window functions drill

Window functions appear in most senior DE SQL screens. Timed practice at [datadriven.io/sql-window-functions-practice](https://datadriven.io/sql-window-functions-practice).

## Python (388 problems)

DE Python is data manipulation, not LeetCode. Common patterns: chunking, sessionization, hash partitioning, interval merging, dedup with tie breaking, streaming aggregation, retries with backoff, schema evolution. Browse at [datadriven.io/python-interview-questions](https://datadriven.io/python-interview-questions).

### Top problems

| Problem | Difficulty | Pattern |
|---|---|---|
| [Batch Records](https://datadriven.io/interview/batch_records) | Easy | Chunking iterables |
| [Column Sum](https://datadriven.io/interview/column_sum) | Easy | Dict aggregation |
| [Activity Time Ledger](https://datadriven.io/interview/activity_time_ledger) | Medium | Interval merging |
| [Batch Partitioner](https://datadriven.io/interview/batch_partitioner) | Medium | Hash bucketing |
| [Batch With Metadata](https://datadriven.io/interview/batch_with_metadata) | Medium | Stateful iteration |
| [Caesar Shift Check](https://datadriven.io/interview/caesar_shift_check) | Hard | String transforms |
| [Character Occurrence Map](https://datadriven.io/interview/character_occurrence_map) | Hard | Counting tradeoffs |

## Schema design (56 problems)

Senior loops are won here. Reward: pick the right grain for fact tables, defend an SCD type, validate the schema with sample queries. Browse at [datadriven.io/data-modeling-interview-questions](https://datadriven.io/data-modeling-interview-questions).

### Top problems

| Problem | Tests |
|---|---|
| [A/B Experiment Assignment Schema](https://datadriven.io/interview/a_b_experiment_assignment_schema) | SCD type 2, sticky bucketing |
| [Customer Address History](https://datadriven.io/interview/customer_address_history) | Effective dates, history preservation |
| [Insurance Claims Lifecycle](https://datadriven.io/interview/insurance_claims_lifecycle) | State machine modeling |
| [Clickstream and Session Schema](https://datadriven.io/interview/clickstream_and_session_schema) | Sessionization, late events |
| [E Commerce Supply Chain Tracking](https://datadriven.io/interview/e_commerce_supply_chain_tracking) | Multi entity tracking |
| [Loan Management Schema](https://datadriven.io/interview/loan_management_schema) | Bridge tables, party roles |
| [Cloud File Storage Metadata Schema](https://datadriven.io/interview/cloud_file_storage_metadata_schema) | Recursive hierarchies |
| [Financial Trading Warehouse](https://datadriven.io/interview/financial_trading_warehouse) | Time series, late arriving facts |
| [Content Engagement Data Model](https://datadriven.io/interview/content_engagement_data_model) | Fact table grain |
| [B2B Invoicing Data Model](https://datadriven.io/interview/b2b_invoicing_data_model) | Many to many with attributes |

## Pipeline architecture (120 problems)

End to end design questions. Use the eight beat framework on every one. Browse at [datadriven.io/data-pipeline-interview-questions](https://datadriven.io/data-pipeline-interview-questions).

### Top case studies

| Case study | Domain |
|---|---|
| [Card Transaction Streaming Pipeline](https://datadriven.io/interview/card_transaction_streaming_pipeline) | Real time, exactly once |
| [Cellular Connectivity and App Log Data Warehouse](https://datadriven.io/interview/cellular_connectivity_and_app_log_data_warehouse) | High cardinality |
| [AWS Pipeline Auto Scaling for Variable Volume](https://datadriven.io/interview/aws_pipeline_auto_scaling_for_variable_volume) | Cost optimization |
| [Connected Vehicle Telemetry Pipeline](https://datadriven.io/interview/connected_vehicle_telemetry_pipeline_with_iac_deployment) | High volume IoT |
| [Capital Markets Intraday Risk Pipeline](https://datadriven.io/interview/capital_markets_intraday_risk_pipeline_with_bcbs_239_lineage) | Regulatory lineage |
| [Database Replication and Schema Normalization Pipeline](https://datadriven.io/interview/database_replication_and_schema_normalization_pipeline) | CDC |
| [Cost Optimized Clickstream Data Lake](https://datadriven.io/interview/cost_optimized_clickstream_data_lake) | Storage tradeoffs |
| [Databricks Pipeline with Spark Performance Optimization](https://datadriven.io/interview/databricks_pipeline_with_spark_performance_optimization) | Spark internals |

## How many problems to be ready

About 100 medium and 25 hard, distributed across the four sections. Past that, returns diminish. Below that, gaps remain.

## Companion repos

- [data-engineering-interview-handbook](https://github.com/datadriven-io/data-engineering-interview-handbook). The flagship handbook with chapter by chapter coverage.
- [data-engineer-interview-handbook](https://github.com/datadriven-io/data-engineer-interview-handbook). 7 day sprint version.
- [awesome-data-engineering-interviews](https://github.com/datadriven-io/awesome-data-engineering-interviews). The DataDriven 75 focused subset.
- [awesome-data-engineering-interview](https://github.com/datadriven-io/awesome-data-engineering-interview). Curated resource list.
- [system-design-for-data-engineers](https://github.com/datadriven-io/system-design-for-data-engineers). 120 long form pipeline case studies.
- [data-engineer-interview-prep](https://github.com/datadriven-io/data-engineer-interview-prep). 8 week structured practice schedule.
- [data-engineering-cheatsheet](https://github.com/datadriven-io/data-engineering-cheatsheet). One page recall reference.

## Contributing

Open an issue with: question text, schema, expected output, what it tests, the common trap. Reviewed and added with attribution.

## License

[CC BY-SA 4.0](LICENSE). Sandboxes hosted at [datadriven.io](https://datadriven.io).
