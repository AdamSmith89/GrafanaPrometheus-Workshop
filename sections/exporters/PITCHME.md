@snap[north span-100]
### Sonarqube Exporter
@snapend

@snap[span-200 midpoint text-10]
- Copy SonarQube exporter to test environment
  - @css[highlight](Windows:) windows/prometheus-sonarqube-exporter/
  - @css[highlight](Mac:) macos-darwin-amd64/prometheus-sonarqube-exporter/
- Run @css[highlight](prometheus-sonarqube-exporter(.exe&#41;)
  - Exporter will keep running if there are no errors
@snapend

---
@snap[north span-100]
### Sonarqube Metrics
@snapend

@snap[span-200 north text-10]
<br><br>
- Navigate to @css[highlight](localhost:9091/metrics)
- Scroll to the bottom to view @css[highlight](metrics)
@snapend
@snap[midpoint]
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
sonarqubeUrl: https://sonarqube.btrusteng.com
sonarqubeUser: serviceaccount
sonarqubePassword: 849176324b1ad53ccd5dc67072a79dd92fbb6df7
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

@snap[span-200 north text-10]
<br><br>
- Add a new @css[highlight](job) to Prometheus
- @css[highlight](Restart) Prometheus
@snapend

@snap[midpoint]
<br><br>
```yaml
- job_name: 'prometheus'
  static_configs:
  - targets: ['localhost:9090']
```
@snapend