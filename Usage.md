# Running HTTP workload generator

Note: These instructions assume you are running the commands from directory:``` /DeathStarBench/```
## Make
```bash
cd wrk2
make
```

## Head to socialNetwork
```bash
cd ../socialNetwork
```

## Tests:
### Test compose post:
```bash
../wrk2/wrk -D exp -t <num-threads> -c <num-conns> -d <duration> -L -s ./wrk2/scripts/social-network/compose-post.lua http://localhost:8080/wrk2-api/post/compose -R <reqs-per-sec>
``` 
where:
| flag           | Meaning                                                                   |
| -------------- | ------------------------------------------------------------------------- |
| -c \<N>        | Connections to keep open                                                  |
| -D \<dist>     | Distributions: fixed, exp, norm, zipf                                     |
| -P             | Print each request latency                                                |
| -p             | Print 99th latency every 0.2s to file under the current working directory |
| -d \<N>        | Duration of test                                                          |
| -t \<N>        | Number of threads to use                                                  |
| -s \<Path>     | Load Lua script file                                                      |
| -H \<Head>     | Add header to request                                                     |
| -L             | Print latency statistics                                                  |
| -S             | Print statistics on different URLs                                        |
| -T \<N>        | Socket/request timeout [unit:s]                                           |
| -B             | Measure latency of whole batches of pipelined ops (as opposed to each op) |
| -r             | Show the number of sent requests                                          |
| -v             | Print version details                                                     |
| -R             | Work rate (throughput) in requests/sec (total) [required param]           |
| Note: for \<N> | Numeric arguments may include a SI unit (1k, 1M, 1G)                      |
| Note: for \<N> | Time arguments may include a SI unit (2s, 2m, 2h                          |


