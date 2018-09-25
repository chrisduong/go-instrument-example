# INSTRUMENTING A GO APPLICATION FOR PROMETHEUS

## How Go exposition works

To expose Prometheus metrics in a Go application, you need to provide a /metrics HTTP endpoint. You can use the prometheus/promhttp library's HTTP Handler as the handler function.

To access the metrics:

```sh
curl http://localhost:2112/metrics
```

## Adding your own metrics

The application above exposes only the default Go metrics. You can also register your own custom application-specific metrics. This example application exposes a `myapp_processed_ops_total` counter that counts the number of operations that have been processed thus far. Every 2 seconds, the counter is incremented by one.
