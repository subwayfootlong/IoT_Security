# Visualize
This folder covers the visualisation function of our project

We used influxdb cloud for our visualization as it is a free cloud service, is secure and has both a visulization and database.

## Security
InfluxDB cloud is secure as it has a token system and also [SSL](https://docs.influxdata.com/influxdb/v2.1/security/enable-tls/)

![image](https://user-images.githubusercontent.com/74981128/150627787-9d2fa4bb-8e19-4699-9829-d0dbc3ca2859.png)

## Flux Sample Query
```
from(bucket: "Carpark Monitoring System")
  |> range(start: v.timeRangeStart, stop: v.timeRangeStop)
  |> filter(fn: (r) => r["_measurement"] == "ABC")
  |> filter(fn: (r) => r["_field"] == "value")
  |> aggregateWindow(every: 1s, fn: last, createEmpty: false)
  |> yield(name: "last")
```
