# Visualize
This folder covers the visualisation function of our project

We used influxdb cloud for our visualization as it is a free cloud service, is secure and has both a visulization and database.

## Security
<!-- InfluxDB cloud is secure as it has a token system and also [Secured Sockets Layer](https://docs.influxdata.com/influxdb/v2.1/security/enable-tls/) (SSL). -->
InfluxDB cloud is secure as it has a token system and enables communication between clients and the InfluxDB server using Transport Layer Security (TLS) encryption. It also allows clients to verify the authenticity of the InfluxDB server when it is configured with a signed TLS certificate also known as Secured Sockets Layer (SSL).

![image](https://user-images.githubusercontent.com/74981128/150627787-9d2fa4bb-8e19-4699-9829-d0dbc3ca2859.png)

### Types of TLS Certificates supported by InfluxDB
- **Single domain** certificates signed by a _Certificate Authority_
  - provides cryptographic security to HTTPS requests and allow clients to verify the identity of the InfluxDB server. Every InfluxDB instance requires a unique single domain certificate The certificates are signed and issued by a trusted, third-party Certificate Authority (CA).
- **Wildcard** certificates signed by a _Certificate Authority_
  - provides cryptographic security to HTTPS requests and allow clients to verify the identity of the InfluxDB server. These certificates can also be used across multiple InfluxDB instances on different servers.
- **Self-signed** certificates
  - are **not signed** by a trusted, third-party _Certificate Authority_. It only provide cryptographic security to HTTPS requests and does not allow clients to verify the identity of the InfluxDB server. Every InfluxDB instance requires a unique self-signed certificate which can be on your own machine.

## Flux Sample Query
```
from(bucket: "Carpark Monitoring System")
  |> range(start: v.timeRangeStart, stop: v.timeRangeStop)
  |> filter(fn: (r) => r["_measurement"] == "ABC")
  |> filter(fn: (r) => r["_field"] == "value")
  |> aggregateWindow(every: 1s, fn: last, createEmpty: false)
  |> yield(name: "last")
```
