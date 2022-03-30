# AssignmentEventsInPool
`toloka.metrics.pool_metrics.AssignmentEventsInPool`

```python
AssignmentEventsInPool(
    self,
    pool_id: str,
    created_name: Optional[str] = None,
    submitted_name: Optional[str] = None,
    accepted_name: Optional[str] = None,
    rejected_name: Optional[str] = None,
    skipped_name: Optional[str] = None,
    expired_name: Optional[str] = None,
    join_events: bool = False,
    *,
    toloka_client: TolokaClient = None,
    timeout: timedelta = ...
)
```

Tracking the change of response statuses in the pool.


The metric is convenient for tracking that the pool is generally "alive" and working.
If you want to track assignments counts, it's better to use AssignmentsInPool.

Metrics starts gathering if they name are set. If the metric name is set to None, they don't gathering.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`pool_id`|**str**|<p>From which pool track metrics.</p>
`created_name`|**Optional\[str\]**|<p>Metric name for a count of created events. Default None.</p>
`submitted_name`|**Optional\[str\]**|<p>Metric name for a count of submitted events. Default &#x27;submitted_events_in_pool&#x27;.</p>
`accepted_name `|**-**|<p>Metric name for a count of accepted events. Default &#x27;accepted_events_in_pool&#x27;.</p>
`rejected_name `|**-**|<p>Metric name for a count of rejected events. Default &#x27;rejected_events_in_pool&#x27;.</p>
`skipped_name`|**Optional\[str\]**|<p>Metric name for a count of skipped events. Default None.</p>
`expired_name`|**Optional\[str\]**|<p>Metric name for a count of expired events. Default None.</p>
`join_events`|**bool**|<p>Count all events in one point.  Default False.</p>

**Examples:**

How to collect this metrics:
```python
def print_metric(metric_dict):
    print(metric_dict)
collector = MetricCollector([AssignmentEventsInPool(pool_id, toloka_client=toloka_client)], print_metric)
asyncio.run(collector.run())
```
## Methods Summary

| Method | Description |
| :------| :-----------|
[get_line_names](toloka.metrics.pool_metrics.AssignmentEventsInPool.get_line_names.md)| Returns a list of metric names that can be generated by this class instance.