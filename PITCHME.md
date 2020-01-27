@snap[text-gold text-30]
Dashboards
@snapend
@css[text-white text-italic text-20](Prometheus and Grafana)

Note:   
- any notes?

---
@snap[north span-100]
### Follow Along
@snapend

@snap[midpoint span-100 text-15 text-center]
[https://gitpitch.com/AdamSmith89/<wbr>GrafanaPrometheus-Workshop](https://gitpitch.com/AdamSmith89/GrafanaPrometheus-Workshop)
@snapend

---
@snap[north span-100]
### Setup Prometheus
@snapend

@snap[span-100 midpoint text-07]
- All resources can be found at @css[highlight](S:\Development\DashboardResources)
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

@snap[span-100 north text-07]
<br><br><br><br>
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

@snap[midpoint text-07]
@ul[list-fade-fragments]
- @css[highlight](Metric:) Describes a general feature of the system being measured<br>@css[highlight](promhttp_metric_handler_requests_total){job="prometheus",...}
- @css[highlight](Labels:) Used to differentiate characteristics of the thing being measured
  - promhttp_metric_handler_requests_total{@css[highlight](job="prometheus"),...}
- @css[highlight](Values:) Result returned by a metric
@ulend
@snapend

@snap[south span-100 text-07]
[Querying Basics](https://prometheus.io/docs/prometheus/latest/querying/basics/) | [Metric Best Practice](https://prometheus.io/docs/practices/naming/)
@snapend

Note:
- Different jobs in Prometheus example; e.g. job="vsts" or job="sonarqube"

---?code=assets/code/prometheus.yml&lang=yaml
@snap[north span-100]
### Prometheus Config
@snapend

@snap[south span-1--]
@[19-23](Jobs define a single endpoint to scrape for data)
@[26-27](Where the data is gathered from)
@snapend

<!-- @snap[west fragment]
@fa[play fa-4x]
@snapend -->