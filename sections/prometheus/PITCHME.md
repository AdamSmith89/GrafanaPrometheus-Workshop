@snap[north span-100]
### Setup Prometheus
@snapend

@snap[span-200 midpoint text-10]
- Copy Prometheus to test environment
  - @css[highlight](Windows:) windows/prometheus-2.14.0.windows-amd64.tar.gz
  - @css[highlight](Mac:) linux/prometheus-2.15.2.linux-amd64.tar.gz
- Run @css[highlight](prometheus(.exe&#41;)
  - Prometheus will keep running if there are no errors
@snapend

---
@snap[north span-100]
### Basic Prometheus Query
@snapend

@snap[span-200 north text-10]
<br><br><br>
- Navigate to @css[highlight](localhost:9090)
- Create a query for @css[highlight](promhttp_metric_handler_requests_total)
- @css[highlight](Execute) it
@snapend
@snap[south span-80]
@img[](assets/img/prometheus-query.png)
@snapend

---
@snap[north span-100]
### Metrics, Labels and Values
@snapend

@snap[midpoint span-200 text-10]
@ul[list-fade-fragments]
- @css[highlight](Metric:) Describes a general feature of the system being measured<br>&#9632; @css[highlight](promhttp_metric_handler_requests_total){job="prometheus",...}
- @css[highlight](Labels:) Used to differentiate characteristics of the thing being measured<br>&#9632; promhttp_metric_handler_requests_total{@css[highlight](job="prometheus"),...}
- @css[highlight](Values:) Result returned by a metric
@ulend
@snapend

@snap[south span-100 text-05]
[Querying Basics](https://prometheus.io/docs/prometheus/latest/querying/basics/) | [Metric Best Practice](https://prometheus.io/docs/practices/naming/)
@snapend

Note:
- Different jobs in Prometheus example; e.g. job="vsts" or job="sonarqube"

---
@snap[north span-100]
### Prometheus Config
@snapend

@snap[midpoint]
```yaml
global:
  scrape_interval:     15s
  evaluation_interval: 15s

alerting:
  alertmanagers:
  - static_configs:
    - targets:

rule_files:

scrape_configs:
  - job_name: 'prometheus'
    static_configs:
    - targets: ['localhost:9090']
```
@snapend

@snap[south span-100]
@[12-13](Jobs define a single endpoint to scrape for data)
@[14-15](Where the data is gathered from)
@snapend