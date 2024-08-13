# tbauriedel.go-carbon

Installs and configures [go-carbon](https://github.com/go-graphite/go-carbon).  

## Variables

`go_carbon_version`: Version (Default: `0.17.3`)  
`go_carbon_storage_dir`: Storage directory (Default: `/var/lib/graphite`)  
`go_carbon_group`: Service user (Default: `carbon`)  
`go_carbon_user`: Service group (Default: `carbon`)  

`go_carbon_max_cpu`: Max CPU (Default: `1`)  
`go_carbon_whisper_workers`: Max workers (Default: `1`)  
`go_carbon_cache_max_size`: Max cache size (Default: `1000000`)  
`go_carbon_udp_enabled`: Enable udp listener (Default: `true`)  
`go_carbon_upd_listen`: UDP listener (Default: `127.0.0.1:2003`)  
`go_carbon_tcp_enabled`: Enable TCP listener (Default: `true`)  
`go_carbon_tcp_listen`: TCP listener (Default: `127.0.0.1:2003`)  
`go_carbon_carbonlink_enabled`: Enable carbonlink listener (Default: `true`)  
`go_carbon_carbonlink_listen`: carbonlink listener (Default: `127.0.0.1:7200`)  
`go_carbon_pickle_enabled`: Enable pickle listener (Default: `true`)  
`go_carbon_pickle_listen`: pickle listener (Default: `127.0.0.1:2004`)  

`go_carbon_logging_file`: Logfile (Default: `/var/log/go-carbon/go-carbon.log`)  
`go_carbon_logging_severity`: Log severity (Default: `warn`)  

`go_carbon_extra_conf:` Add some extra custom configuration  

`go_carbon_storage_schemas`: List of storage retentions (Default: [here](defaults/main.yml))  
`go_carbon_storage_schemas.name`: Name of schema  
`go_carbon_storage_schemas.pattern`: Pattern that should match  
`go_carbon_storage_schemas.retentions`: Retention policy  
`go_carbon_storage_schemas.compressed`: Enable compression (Default: `false`)

`go_carbon_storage_aggregation`: Add storage aggrgation  
