# Visualize
This folder covers the visualisation function of our project

We used influxdb cloud for our visualization as its free on the cloud for up to a certain writes

It has both a database and a simple visualization software

## Sample Query
`from(bucket: "Carpark Monitoring System")

  |> range(start: v.timeRangeStart, stop: v.timeRangeStop)
  
  |> filter(fn: (r) => r["_measurement"] == "ABC")
  
  |> filter(fn: (r) => r["_field"] == "value")
  
  |> aggregateWindow(every: 1s, fn: last, createEmpty: false)
  
  |> yield(name: "last")`
