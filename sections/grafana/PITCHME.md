@snap[north span-100]
### Setup Grafana
@snapend

@snap[span-100 midpoint text-09]
- @css[highlight](Windows:)
  - Copy and Extract windows/grafana-6.5.1.windows-amd64.zip
- @css[highlight](Mac:)
  - brew update
  - brew install grafana
- @css[highlight](Linux:)
  - Copy and Extract linux/grafana-6.5.2.linux-amd64.tar.gz
- Run @css[highlight](bin/grafana-server(.exe&#41;)
  - Prometheus will keep running if there are no errors
@snapend