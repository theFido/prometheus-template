# Prometheus + Grafana

# PromQL

## Rate vs increase

Interval: Sampling window, specified with square brackets after the metric name.

Increase: Number of samples per minute.

Rate: Per-second average.

**Scenario:** 120 requests at the same time:

| Function/Interval |  1m |  2m |
|-------------------|-----|-----|
| Rate              | 120 |  60 |
| Increase          | 120 | 120 |

Increasing the interval when using rate has two effects:

- Smooths the lines in the chart.
- Hides the spike in the first minute, and produces a misleading data point in 
the second minute (since it will represent 60 too).

[🔗  - More information](https://prometheus.io/docs/prometheus/latest/querying/functions/)