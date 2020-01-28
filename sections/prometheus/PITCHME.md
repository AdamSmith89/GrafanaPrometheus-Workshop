@snap[north span-100]
### Setup Prometheus
@snapend

@snap[span-100 midpoint text-09]
- Copy Prometheus to test environment
  - @css[highlight](Windows:) windows/prometheus-2.14.0.windows-amd64.tar.gz
  - @css[highlight](Mac:) darwin/prometheus-2.15.2.darwin-amd64.tar.gz
- Extract the @css[highlight](.gz) then the @css[highlight](.tar)
- Run @css[highlight](prometheus(.exe&#41;)
  - Prometheus will keep running if there are no errors
@snapend

---
@snap[north span-100]
### Basic Prometheus Query
@snapend

@snap[span-100 north text-09]
<br><br>
- Navigate to @css[highlight](localhost:9090)
- Create a query for @css[highlight](promhttp_metric_handler_requests_total)
- @css[highlight](Execute) it
- Separately navigate to @css[highlight]([localhost:9090/metrics]())
- @css[highlight](Refresh) to update query total
@snapend
@snap[south span-70 move-down-10]
@img[](assets/img/prometheus-query.png)
@snapend

---
@snap[north span-100]
### Metrics, Labels and Values
@snapend

@snap[midpoint span-100 text-09]
@ul[list-fade-fragments]
- @css[highlight](Metric:) General feature of the system being measured<br>&#9632; @css[highlight](promhttp_metric_handler_requests_total)<br>@css[text-indent-1]({)job="prometheus",...}
- @css[highlight](Labels:) Differentiates characteristics of the metric<br>&#9632; promhttp_metric_handler_requests_total<br>@css[text-indent-1]({)@css[highlight](job="prometheus"),...}<br>@css[text-indent-1]({)@css[highlight](job="sonarqube"),...}
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
### Prometheus Configuration
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
@[14-15](Targets define Where the data is gathered from)
@snapend