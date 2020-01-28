@snap[north span-100]
### Setup Grafana
@snapend

@snap[span-100 midpoint text-09]
- @css[hl-westside](Windows:)
  - Copy and Extract windows/grafana-6.5.1.windows-amd64.zip
- @css[hl-westside](Mac:)
  - brew update
  - brew @css[hl-alizarin](install) grafana
- @css[hl-westside](Linux:)
  - Copy and Extract linux/grafana-6.5.2.linux-amd64.tar.gz
- Run @css[hl-westside](bin/grafana-server(.exe&#41;)
  - Grafana will keep running if there are no errors
@snapend

---
@snap[north span-100]
### Prometheus In Grafana
@snapend

@snap[span-100 north text-09]
- Navigate to @css[hl-westside](localhost:3000)
- @css[hl-westside](User): admin, @css[hl-westside](Pass): admin
@snapend

@snap[west]
@img[](assets/img/grafana-add-datasource.png)
@snapend
@snap[midpoint]
@img[](assets/img/grafana-add-prometheus.png)
@img[](assets/img/grafana-add-prometheus-url.png)
@snapend
@snap[east]
@img[](assets/img/grafana-add-prometheus-save.png)
@snapend