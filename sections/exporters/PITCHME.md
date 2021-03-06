@snap[north span-100]
### Sonarqube Exporter
@snapend

@snap[span-100 midpoint text-09]
- Copy SonarQube exporter to test environment
  - @css[hl-westside](Windows:) windows/prometheus-sonarqube-exporter/
  - @css[hl-westside](Mac:) darwin/prometheus-sonarqube-exporter/
  - @css[hl-westside](Linux:) linux/prometheus-sonarqube-exporter/
- Run @css[hl-westside](prometheus-sonarqube-exporter(.exe&#41;)
  - Exporter will keep running if there are no errors
@snapend

Note:
- Jack

---
@snap[north span-100]
### Sonarqube Metrics
@snapend

@snap[span-100 north text-09]
<br><br>
- Navigate to @css[hl-westside](localhost:9091/metrics)
- Scroll to the bottom to view @css[hl-westside](metrics)
@snapend
@snap[midpoint span-110]
<br><br>
```ps
...
# HELP sonarqube_measures_bugs Bugs in a project
# TYPE sonarqube_measures_bugs gauge
sonarqube_measures_bugs{projectKey="defendpoint-releasestatic"} 139
# HELP sonarqube_measures_codesmells Code smells in a project
# TYPE sonarqube_measures_codesmells gauge
sonarqube_measures_codesmells{projectKey="defendpoint-releasestatic"} 5203
# HELP sonarqube_measures_new_bugs New bugs in a project
# TYPE sonarqube_measures_new_bugs gauge
sonarqube_measures_new_bugs{projectKey="defendpoint-releasestatic"} 0
...
```
@snapend

---
@snap[north span-100]
### Sonarqube Configuration
@snapend

@snap[midpoint]
<br>
```yaml
# Defined in seconds
globalScrapeTime: 120
listenOnPort: 9091
sonarqubeUrl: ...
sonarqubeUser: ...
sonarqubePassword: ...
measures:
  projects:
  - "defendpoint-releasestatic"
#  - "mac-client"
#  - "Avecto-Data-EventSimulator"
#  - "pmc-saas-portal"
  metrics:
  - bugs
  - new_bugs
  - code_smells
  - new_code_smells
  - vulnerabilities
  - new_vulnerabilities
```
@snapend

@snap[south span-100]
@[3](Output port)
@[4-6](Connection information)
@[8-12](Projects to query)
@[13-19](Metrics to query)
@snapend

---
@snap[north span-100]
### Sonarqube In Prometheus
@snapend

@snap[span-100 north text-09]
<br><br><br>
- Add a new @css[hl-westside](job) to Prometheus
- @css[hl-westside](Restart) Prometheus
@snapend

@snap[midpoint]
<br><br>
```yaml
- job_name: 'sonarqube'
  static_configs:
  - targets: ['localhost:9091']
```
@snapend

@snap[south span-100]
@[3](Ensure port is the same port configured in the exporter)
@snapend

---
@snap[north span-100]
### Sonarqube In Prometheus
@snapend

@snap[span-100 north text-09]
<br><br><br>
- Navigate back to Prometheus (@css[hl-westside](localhost:9090))
- Create a query for @css[hl-westside](sonarqube_measures_bugs)
- @css[hl-westside](Execute) it
  - May take a minute due to scrape intervals
@snapend

@snap[south span-70]
@img[](assets/img/sonarqube-query.png)
@snapend

---
@snap[north span-100]
### PromQL
@snapend

@snap[midpoint span-100]
- @css[hl-westside](5 minutes) to play with Sonarqube metrics
- Ideas;
  - Track more @css[hl-westside](projects)
  - Single metric for @css[hl-westside](bugs) and @css[hl-westside](code smells)
@snapend

@snap[south span-100 text-05]
[Query Examples](https://prometheus.io/docs/prometheus/latest/querying/examples/)
@snapend

Note:
- Total bugs across projects is a good one but the sum function has to be used as the metric labels need to be the same for the basic + operator.