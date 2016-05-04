## Vertx React Example

This is a simple proof-of-concept testing the use of Vert.x for React server-side rendering. It was adapted from
https://github.com/kucharzyk/java-ssr-benchmark and also uses Webpack for bundling.

To run the project:
`gradle clean build`

and then:
`gradle start`

Website is at: http://localhost:8999

To benchmark with Apache HTTP server benchmark tool, use:
`ab -n 10000 -c150 http://localhost:8999/web`

And get something like this:

```
This is ApacheBench, Version 2.3 <$Revision: 1638069 $>
Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/
Licensed to The Apache Software Foundation, http://www.apache.org/

Benchmarking localhost (be patient)
Completed 1000 requests
Completed 2000 requests
Completed 3000 requests
Completed 4000 requests
Completed 5000 requests
Completed 6000 requests
Completed 7000 requests
Completed 8000 requests
Completed 9000 requests
Completed 10000 requests
Finished 10000 requests


Server Software:
Server Hostname:        localhost
Server Port:            8999

Document Path:          /web
Document Length:        689 bytes

Concurrency Level:      150
Time taken for tests:   1.936 seconds
Complete requests:      10000
Failed requests:        0
Total transferred:      7290000 bytes
HTML transferred:       6890000 bytes
Requests per second:    5164.18 [#/sec] (mean)
Time per request:       29.046 [ms] (mean)
Time per request:       0.194 [ms] (mean, across all concurrent requests)
Transfer rate:          3676.46 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    0   0.9      0      11
Processing:     3   29   4.0     27      55
Waiting:        3   29   4.0     27      55
Total:         13   29   4.0     27      57

Percentage of the requests served within a certain time (ms)
  50%     27
  66%     29
  75%     30
  80%     33
  90%     34
  95%     35
  98%     36
  99%     45
 100%     57 (longest request)

```