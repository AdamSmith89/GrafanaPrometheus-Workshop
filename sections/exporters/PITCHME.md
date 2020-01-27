@snap[north span-100]
### Exporters
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
### Basic Prometheus Query
@snapend

@snap[span-200 north text-10]
<br><br>
- Navigate to @css[highlight](localhost:9091/metrics)
- Scroll to the bottom
@snapend
@snap[south]
```ps
# HELP sonarqube_measures_bugs Bugs in a project
# TYPE sonarqube_measures_bugs gauge
sonarqube_measures_bugs{projectKey="defendpoint-releasestatic"} 139
# HELP sonarqube_measures_codesmells Code smells in a project
# TYPE sonarqube_measures_codesmells gauge
sonarqube_measures_codesmells{projectKey="defendpoint-releasestatic"} 5203
# HELP sonarqube_measures_new_bugs New bugs in a project
# TYPE sonarqube_measures_new_bugs gauge
sonarqube_measures_new_bugs{projectKey="defendpoint-releasestatic"} 0
# HELP sonarqube_measures_new_codesmells New code smells in a project
# TYPE sonarqube_measures_new_codesmells gauge
sonarqube_measures_new_codesmells{projectKey="defendpoint-releasestatic"} 6
# HELP sonarqube_measures_new_vulnerabilities new vulnerabilities in a project
# TYPE sonarqube_measures_new_vulnerabilities gauge
sonarqube_measures_new_vulnerabilities{projectKey="defendpoint-releasestatic"} 0
# HELP sonarqube_measures_vulnerabilities vulnerabilites in a project
# TYPE sonarqube_measures_vulnerabilities gauge
sonarqube_measures_vulnerabilities{projectKey="defendpoint-releasestatic"} 0
```
@snapend