# InfluxDB-metrics-collectors
Collection of python scripts for collecting metrics for InfluxDB
The scripts are meant to be executed by Telegraf. Each directory contains configuration for /etc/telegraf/telegraf.d/.

Example setting up a database:
```
create database htcondor
create user writer_htcondor with password 'mypassword'
grant write on htcondor to writer_htcondor
create retention policy OneMonth on htcondor duration 720h replication 1 default
```
