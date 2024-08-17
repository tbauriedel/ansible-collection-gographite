# tbauriedel.gocarbon

Installs and configures [go-carbon](https://github.com/go-graphite/go-carbon).  

## Variables

A detailed documentation can be found inside of the [official go-carbon repo](https://github.com/go-graphite/go-carbon?tab=readme-ov-file#configuration).  

Default variables are defined [here](defaults/main.yml).  

`gocarbon_version`: Version (Default: `0.17.3`)  
`gocarbon_storage_dir`: Storage directory (Default: `/var/lib/graphite`)  
`gocarbon_group`: Service user (Default: `carbon`)  
`gocarbon_user`: Service group (Default: `carbon`)  

`gocarbon_max_cpu`: Max CPU (Default: `1`)  
`gocarbon_whisper_workers`: Max workers (Default: `1`)  
`gocarbon_cache_max_size`: Max cache size (Default: `1000000`)  
`gocarbon_udp_enabled`: Enable udp listener (Default: `true`)  
`gocarbon_upd_listen`: UDP listener (Default: `127.0.0.1:2003`)  
`gocarbon_tcp_enabled`: Enable TCP listener (Default: `true`)  
`gocarbon_tcp_listen`: TCP listener (Default: `127.0.0.1:2003`)  
`gocarbon_carbonlink_enabled`: Enable carbonlink listener (Default: `true`)  
`gocarbon_carbonlink_listen`: carbonlink listener (Default: `127.0.0.1:7200`)  
`gocarbon_pickle_enabled`: Enable pickle listener (Default: `true`)  
`gocarbon_pickle_listen`: pickle listener (Default: `127.0.0.1:2004`)  
`gocarbon_carbonserver_enabled`: Enable carbonserver (Default: `true`)  
`gocarbon_carbonserver_listen`: carbonserver listener: (Default: `127.0.0.1:8080`)

`gocarbon_logging_file`: Logfile (Default: `/var/log/go-carbon/go-carbon.log`)  
`gocarbon_logging_severity`: Log severity (Default: `warn`)  

`gocarbon_extra_conf:` Add some extra custom configuration  

`gocarbon_storage_schemas`: List of storage retentions (Default: [here](defaults/main.yml))  
`gocarbon_storage_schemas.name`: Name of schema  
`gocarbon_storage_schemas.pattern`: Pattern that should match  
`gocarbon_storage_schemas.retentions`: Retention policy  
`gocarbon_storage_schemas.compressed`: Enable compression (Default: `false`)

`gocarbon_storage_aggregation`: Add storage aggregation

## Config file

If you dont add some custom configuration, the go-carbon.conf will look like this.  
```
#
# Ansible managed
#

[common]
user = "carbon"
graph-prefix = "carbon.agents.{host}"
metric-endpoint = "local"
max-cpu = 1
metric-interval = "1m0s"

[whisper]
data-dir = "/var/lib/graphite/whisper/"
schemas-file = "/etc/go-carbon/storage-schemas.conf"
aggregation-file = ""
quotas-file = ""
workers = 1
max-updates-per-second = 0
sparse-create = false
physical-size-factor = 0.75
flock = false
compressed = false
enabled = true
hash-filenames = true
remove-empty-file = false
online-migration = false
online-migration-rate = 5
online-migration-global-scope = ""

[cache]
max-size = 1000000
write-strategy = "max"

[carbonserver]
listen = "127.0.0.1:8080"
enabled = true

[udp]
listen = "127.0.0.1:2003"
enabled = true
buffer-size = 0

[tcp]
listen = "127.0.0.1:2003"
enabled = true
buffer-size = 0
compression = ""

[carbonlink]
listen = "127.0.0.1:7200"
enabled = true
read-timeout = "30s"

[pickle]
listen = "127.0.0.1:2004"
max-message-size = 67108864
enabled = true
buffer-size = 0


[[logging]]
logger = ""
file = "/var/log/go-carbon/go-carbon.log"
level = "warn"
encoding = "mixed"
encoding-time = "iso8601"
encoding-duration = "seconds"
sample-tick = ""
sample-initial = 0
sample-thereafter = 0
```
