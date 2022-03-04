# Imposter CSV example

Run:

    imposter up

Test:

```
curl -v http://localhost:8080/example
*   Trying ::1:8080...
* Connected to localhost (::1) port 8080 (#0)
> GET /example HTTP/1.1
> Host: localhost:8080
> User-Agent: curl/7.77.0
> Accept: */*
>
* Mark bundle as not supporting multiuse
< HTTP/1.1 200 OK
< X-Imposter-Request: b1e38a5e-589c-4d44-aacc-e976dca1d81f
< Server: imposter
< Content-Type: text/csv
< content-length: 77
<
Firstname,Lastname,Email
Jane,Doe,jane@example.com
John,Doe,john@example.com
* Connection #0 to host localhost left intact
```

Logs:

```
113:26:20 INFO  i.g.i.Imposter - Starting mock engine 2.9.0
...
3:27:05 DEBUG i.g.i.p.r.RestPluginImpl - Adding handler: GET -> /example
13:27:05 INFO  i.g.i.Imposter - Mock engine up and running on http://localhost:8080
13:27:17 DEBUG i.g.i.h.AbstractResourceMatcher - Matched resource config for GET /example
13:27:17 DEBUG i.g.i.s.ResponseRoutingServiceImpl - Using default HTTP 200 response behaviour for request: GET http://localhost:8080/example
13:27:17 INFO  i.g.i.p.r.RestPluginImpl - Handling GET object request for: http://localhost:8080/example
13:27:17 INFO  i.g.i.s.ResponseServiceImpl - Serving response file data.csv for URI http://localhost:8080/example with status code 200
13:27:17 DEBUG i.g.i.s.ResponseServiceImpl - Inferred text/csv content type
```
