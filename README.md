# InfluxDB-metrics-collectors
Collection of python scripts for collecting metrics for InfluxDB

* **metrics-influxdb-arc**: general ARC CE metrics
* **metrics-influxdb-condor-gangliad**: replacement for gmetric to be used with condor_gangliad
* **metrics-influxdb-condor-general**: general HTCondor pool metrics
* **metrics-influxdb-condor-jobs**: numbers of jobs and cores by VO and schedd in different states
* **metrics-influxdb-condor-multistartjobs**: numbers of jobs which have run more than once
* **metrics-influxdb-condor-schedd**: numbers of shadow exits by state
* **metrics-influxdb-fts3-active**: active transfers by VO and by schedd
* **metrics-influxdb-fts3-http**: HTTP response code frequency and response duration
* **metrics-influxdb-squid**: squid metrics
* **metrics-influxdb-zookeeper**: ZooKeeper metrics
* **metrics-influxdb-mesos-master**: Mesos master metrics
* **metrics-influxdb-mesos-agent**: Mesos agent metrics
* **metrics-influxdb-mesos-tasks**: Resource usage metrics from cAdvisor tagged by information from Mesos

All scripts read config files with names of the form _/usr/local/etc/influxdb-xx.conf_ which specify the database connection details. An example is included. The scripts should be run as crons, generally every minute.

Before running any of the above scripts the appropriate databases, users and retention policies will need to be created in InfluxDB. For example, in the InfluxDB shell:
```
create database htcondor
create user writer_htcondor with password 'mypassword'
grant write on htcondor to writer_htcondor
create retention policy OneMonth on htcondor duration 720h replication 1 default
```
