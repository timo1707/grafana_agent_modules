# grafana_agent_modules

a simple [Grafana Agent Flow](https://grafana.com/docs/agent/latest/) Configuration for windows clients with preconfigured metrics and logs modules.

The Metrics module has predifined [windows exporter](https://grafana.com/docs/agent/latest/flow/reference/components/prometheus.exporter.windows/) collectors and [windows services](https://grafana.com/docs/agent/latest/flow/reference/components/prometheus.exporter.windows/#service-block) which can be extendet with the environment variables `flow_collector` and `flow_service`

## Agent Version

`>= v0.33`

## Module arguments

The following arguments are supported when passing arguments to the module
loader:

| Name | Type | Description | Default | Required
| ---- | ---- | ----------- | ------- | --------
| `enabled_collectors`  | `string`   | Windows Exporter Collector. | `["cpu", "cs", "logical_disk", "net", "os", "service", "system"]` | no
| `enabled_service` | `string` | Windows Service to collect. | `"Name = 'service1' OR Name = 'service2' OR Name = 'service3'"` | no

additional arguments cann be passed as Environment Variables:

collectors can be set up as environment variables
`setx flow_collector "cpu_info" /m`

additional services can be set up as environment variables
`setx flow_service "OR Name = 'Grafana Agent Flow'" /m`