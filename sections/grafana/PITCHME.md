@snap[north span-100]
### Setup Grafana
@snapend

@snap[span-100 midpoint text-09]
- @css[hl-westside](Windows:)
  - Copy and Extract<br>windows/grafana-6.5.1.windows-amd64.zip
- @css[hl-westside](Mac:)
  - brew update
  - brew @css[hl-alizarin](install) grafana
- @css[hl-westside](Linux:)
  - Copy and Extract<br>linux/grafana-6.5.2.linux-amd64.tar.gz
- Run @css[hl-westside](bin/grafana-server(.exe&#41;)
  - Grafana will keep running if there are no errors
@snapend

---
@snap[north span-100]
### Grafana Data Source
@snapend

@snap[span-100 midpoint text-09]
- Navigate to @css[hl-westside](localhost:3000)
- @css[hl-westside](User): admin, @css[hl-westside](Pass): admin
- Choose @css[hl-westside](Add data source)
- @css[hl-westside](Select) Prometheus
- Add @css[hl-westside](http://localhost:9090) as the @css[hl-westside](URL)
- Press @css[hl-westside](Save & Test)
@snapend

@snap[south span-100]
@img[](assets/img/grafana-datasource-working.png)
@snapend

---
@snap[north span-100]
### Grafana Graph Panel
@snapend

@snap[span-100 midpoint text-09]
- Navigate @css[hl-westside](Home) (@css[hl-westside](localhost:3000)&#41;
- Select @css[hl-westside](New dashboard) then @css[hl-westside](Add Query)
- Use @css[hl-westside](promhttp_metric_handler_requests_total) for @css[hl-westside](query)
- Filter query; @css[hl-westside](job): prometheus, @css[hl-westside](code): 200
- Refresh @css[hl-westside](localhost:9090/metrics) to update
- Use @css[hl-westside](Go Back) button to see panel on dashboard
@snapend

---
@snap[north span-100]
### Grafana SingleStat Panel
@snapend

@snap[span-100 midpoint text-09]
- On Dashboard select @css[hl-westside](Add panel) (top-right)
- Select @css[hl-westside](Choose Visualization)
- Choose @css[hl-westside](Singlestat) and change @css[hl-westside](Show) to @css[hl-westside](Current)
- Switch to @css[hl-westside](Queries) (left)
- Use any @css[hl-westside](Sonarqube) query from earlier
- Use @css[hl-westside](Go Back) button to see panel on dashboard
@snapend

---
@snap[north span-100]
### Free Play
@snapend

@snap[span-100 midpoint text-09]
- @css[hl-westside](Remaining time) to play with panels
- Ideas;
  - Add @css[hl-westside](Thresholds) to Sonarqube panel
  - Use @css[hl-westside](Value Mappings) on Sonarqube panel
  - Apply a @css[hl-westside](rate) function to Prometheus panel
@snapend

@snap[south span-100 text-05]
[Querying Functions](https://prometheus.io/docs/prometheus/latest/querying/functions/)
@snapend