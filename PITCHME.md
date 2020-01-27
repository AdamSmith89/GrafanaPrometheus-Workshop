@snap[text-gold text-20]
Dashboards
@snapend
@css[text-black text-italic text-04 fragment](Prometheus and Grafana)

Note:   
- any notes?

---
@snap[north span-100]
### Follow Along?
@snapend

@snap[mid-point span-100]
[Slides](https://gitpitch.com/AdamSmith89/GrafanaPrometheus-Workshop#/)
@snapend

---
@snap[north span-100]
### Setup Prometheus
@snapend

@ul
- Copy Prometheus to test environment
  - **Windows:** S:\Development\DashboardResources\windows\prometheus-2.14.0.windows-amd64.tar.gz
  - **Mac:** S:\Development\DashboardResources\linux\prometheus-2.15.2.linux-amd64.tar.gz
- Run **prometheus.exe**
- Navigate to **localhost:9090**
- Create a query for **promhttp_metric_handler_requests_total** and **Execute** it
  - Picture?
@ulend

---
@snap[north span-100]
### Terminology: Metrics, Labels and Values
@snapend

@ul
- **Metric:** Describes a general feature of the system being measured
  - code snippet highlighting metric name
- **Labels:** Used to differentiate characteristics of the thing being measured
  - code snippet highlighting label
- **Values:** Result returned by a metric
@ulend

[Querying Basics](https://prometheus.io/docs/prometheus/latest/querying/basics/)
<br>
[Metric Best Practicses](https://prometheus.io/docs/practices/naming/)

Note:
- Different jobs in Prometheus example; e.g. job="vsts" or job="sonarqube"
---
@snap[north span-100]
### Prometheus Config
@snapend

@snap[mid-point]
So why did that work?

- config code snippet highlighting the different bits
@snapend

<!-- @snap[west fragment]
@fa[play fa-4x]
@snapend -->