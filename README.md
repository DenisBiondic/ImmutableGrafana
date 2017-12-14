# Immutable Grafana

Immutable Grafana with dashboard &amp; datasource as code

Test / build / play around with
```
docker-compose up
```

- Grafana *localhost:3000* (admin admin credentials) - Should be configured with a datasource and a dashboard
- Prometheus *localhost:9090*

If you need to rebuild the containers, simply use

```
docker-compose up --build
```

Purpose of this project is to showcase how to package different grafana configurations directly into a custom grafana image. 

- For the **datasource**, a Prometheus container is also started with docker-compose, and the datasource configuration automatically uses this prometheus instance
- For the **dashboard**, a custom dashboard using some Prometheus metrics is also baked into the image 

Workflow for editing / saving a custom dashbord is simply:
- edit the dashboard directly in grafana
- export the dashboard to JSON
- save the JSON file here in sources (dashboard folder)

# Important

This feature is only available in grafana master branch, and is scheduled to be release with Grafana 4.7! Check here: https://github.com/grafana/grafana/milestone/72
