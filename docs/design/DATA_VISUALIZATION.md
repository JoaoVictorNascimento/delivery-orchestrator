# Data Visualization and Metric Semantics

## Approved chart inventory

| View | Chart | Meaning |
|---|---|---|
| AI Usage / Overview | Area | Daily reported tokens by provider |
| AI Usage / Overview | Donut | Mutually exclusive token composition or grouping (project/provider/stage) |
| AI Usage / Efficiency | Heatmap | Local weekday/hour token intensity |
| AI Usage / Efficiency | Scatter | Execution duration × attributable reported tokens |
| AI Usage / Experiments | Radar | Baseline vs variant on efficiency, quality, speed, consistency and success |
| Insights / Performance | Area, donut, scatter | Started/ready trend, outcome distribution, elapsed vs human wait |
| Insights / Quality | Compact project comparison | Recurrence and quality rates with sample counts |
| Insights / Autonomy | Radar | Observable delivery rates, no arbitrary composite score |

Use Recharts/shadcn Charts and custom SVG heatmap. No additional chart library required by design. Two main charts per AI Usage overview/efficiency tab and one radar in Experiments; concise tables for details. Use amber/taupe for series, semantic green/red only for meaningful outcomes, visible legends, units, responsive axes and tooltips. No excessive cards; max four headline indicators per analytic view. Provide accessible table and selection equivalent. Share filter scope and timestamps across metrics.

## Telemetry contract requirements (conceptual, not API schema)

Capture provider, integration/version, model/version where known, execution/turn identity, delivery/project, skill/version, workflow stage, observed timestamp, raw metric semantics and normalized counters, source and coverage status. Distinguish cumulative counters from increments; deduplicate by stable event/turn identity and reconcile restarts. Keep original sanitized metadata for audit; do not store full prompts just to count tokens. Avoid duplicate attribution to finding, delivery and stage; report shared overhead separately. Unavailable, partial and estimated measurements must be distinguishable. Only verified compatible counters can be aggregated across providers.

For providers where cached input is a subset of total input, uncached input = input minus cached input; total = input + output. Some providers report separate cache read/write counters; normalize only after confirming their semantics. Reasoning count may be a subset of output, not an additive category. Show missing category rather than infer zero. Costs and quotas require reported data or explicitly labeled estimates; subscription usage is not equivalent to API billing.

## Metric definitions

| Metric | Definition / caveat |
|---|---|
| Reported total tokens | Sum of compatible observed non-duplicated token totals in selected scope; disclose partial coverage |
| Median observed delivery | Median of attributable totals over comparable deliveries with sufficient coverage; define eligibility |
| Cached input share | Cached input / total input for records with known compatible cache/input counts; denominator zero = unavailable |
| Telemetry coverage | Eligible executions with complete required counters / eligible executions; show counts and partial records |
| Retry consumption | Tokens attributable to retry attempts, separately from initial execution; no assumed missing totals |
| Tokens per successful run/delivery | Attributable reported tokens including eligible retries / successful eligible count, coverage and scope explicit |
| Tokens per confirmed finding | Only use direct or documented allocation; shared costs not silently duplicated |
| Token reduction | (baseline median − variant median) / baseline median; same task/model/snapshot where feasible; baseline zero unavailable |
| Delivery lead time | Start to current MergeReady; completion time separate |
| Human waiting | Union of waiting intervals within delivery, not active work |
| Human touch time | Measured active participation only, unknown when unavailable |
| Merge-ready rate | Ready deliveries / defined observed cohort; exclude/label open and censored cases according to documented cohort |
| First-pass rate | Eligible completed MRs ready without external correction / eligible completed MRs |
| Recurrence rate | Confirmed findings matching known rules / deduplicated confirmed findings |
| Deliveries without recurrence | Eligible observed deliveries with no confirmed recurring issue / eligible deliveries |
| Automation share | Automated executed workflow steps / comparable recorded steps; retries and counting unit explicit |
| Decisions per delivery | Distinct decided human requests / eligible deliveries |

Show sample size, period, timezone, source, denominators and last updated. Do not imply productivity gains without comparable baseline and complexity. A decrease in findings can indicate worse detection; pair with verification. No target that incentivizes bypassing human safeguards.

## Experiment protocol (P2 runner)

Freeze task/snapshot, rules and skill versions, model/effort and tools; document warm/cold cache and environment; use disposable worktrees, multiple runs, known expected findings/tests and quality criteria. Record tokens, duration, success, false positives/negatives and variability. Compare absolute results in table; radar uses explicitly documented 0–100 transforms with same reference and direction (higher better). Do not invent normalization where sample missing; omit unavailable dimension or chart and explain. Quality gate remains separate and mandatory; no combined score can override it. RTK and Context Mode are candidate research tools, not dependencies or verified savings. CSV/JSON exports omit secrets and sensitive code; demo labels preserved.
