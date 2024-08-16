# tbauriedel.carbonapi

Installs and configures [carbonapi](hthttps://github.com/go-graphite/carbonapi).  

## Variables

A detailed documentation can be found inside of the [official carbonapi repo](https://github.com/go-graphite/carbonapi/blob/main/doc/configuration.md).  

If you are not sure how to use the variables, check the defaults.  
Default variables are defined [here](defaults/main.yml).

`carbonapi_version`: Version (Default: `0.16.0`)  
`carbonapi_version`: Service user (Default: `carbon`)  

`carbonapi_listeners`: List of listener (Default: `['127.0.0.1:8888']`)  
`carbonapi_prefix`: Specify prefix for all URLs  
`carbonapi_caching_dns_resolver`: Custom DNS resolver (Default: `false`)  
`carbonapi_caching_dns_time`: TTL for DNS records to be valid (Default: `1m`)  
`carbonapi_expvar`: Controls expvar  
`carbonapi_charsets`: List of charsets (Default `['Lating]`)  
`carbonapi_pass_headers`: Define headers to pass  
`carbonapi_log_headers`: Define headers that will be logged  
`carbonapi_defines`: List of custom function aliases  
`carbonapi_not_found_rc`: Default RC for 'not found' (Default: `200`)  
`carbonapi_concurency`: Max metric requests that can be fetched in parallel (Default: `1000`)  
`carbonapi_cache`: Specify cache  
`carbonapi_cpus`: Max cpu cores to use (Default `0` - unlimited)  
`carbonapi_timezone`: Time zone  
`carbonapi_extract_tags_form_args`: Extract tags from seriesByTag arguments (Default: `false`)  
`carbonapi_functions_config`: Extra config files for specific functions  
`carbonapi_max_batch_size`: Max number of metrics per request (Default: `100`)  
`carbonapi_graphite`: Specify configuration on how to send internal metrics to graphite  
`carbonapi_max_idle_conns`: Max idle connections (Default: `10`)
`carbonapi_pid_file`: PID file  
`carbonapi_slow_log`: Threshold for slow requests to be logged (Default: `3s`)  
`carbonapi_timeouts`:  Timeout definitions  
`carbonapi_timeouts.find`: (Default: `2s`)  
`carbonapi_timeouts.render`: (Default: `10s`)  
`carbonapi_timeouts.connect`: (Default: `500ms`)  
`carbonapi_concurrency_limit_per_server`: Limit of max connections per server (Default: `0`)  
`carbonapi_keepalive_interval`: KeepAlive interval (Default: `30s`)  
`carbonapi_backends`: List of backend groups (Default: `["http://127.0.0.1:8080"]`)  
`carbonapi_backendsv2`: Configuration for backends (Default: One backend is defined via default See below)  
`carbonapi_backendsv2.groupname`: Name of the carbonapi's backend (Default: `group1`)  
`carbonapi_backendsv2.protocol`: Protocol for the backend (Default: `auto`)  
`carbonapi_backendsv2.lb_method`: Load-balancing method (Default: `broadcast`)  
`carbonapi_backendsv2.max_tries`: Amount of retries if query fails (Default: `3`)  
`carbonapi_backendsv2.servers`: List of sever URLs in this backend groups (Default: `["http://localhost:8080]`)

## Config file

If you dont add some custom configuration, the carbon-api.yaml will look like this.  
```
#
# Ansible managed
#

listeners:
  - address: "127.0.0.1:8888"
prefix: ""
useCachingDNSResolver: false
cachingDNSRefreshTime: "1m"
expvar:
  enabled: false
  pprofEnabled: false
  listen: ""
unicodeRangeTables:
  - "Latin"
notFoundStatusCode: 200
concurency: 1000
cpus: 0
tz: ""
extractTagsFromArgs: False
maxBatchSize: 100
idleConnections: 10
pidFile: ""
upstreams:
    slowLogThreshold: "3s"
    timeouts:
        find: "2s"
        render: "10s"
        connect: "500ms"
    concurrencyLimitPerServer: 0
    keepAliveInterval: "30s"
    maxIdleConnsPerHost: 10
    backends:
        - "http://127.0.0.1:8080"
    backendsv2:
      backends:
        -
          groupName: group1
          protocol: auto
          lbMethod: broadcast
          maxTries: 3
          servers:
            - "http://127.0.0.1:8080"
```