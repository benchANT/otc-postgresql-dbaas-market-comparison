# PostgreSQL DBaaS Market Comparison: AWS RDS for PostgreSQL - MS Azure Database for PostgreSQL Flexible Server - OTC RDS PostgreSQL 

This repository contain the raw performance data and metadata of the associated PostgreSQL DBaaS market comparison [Open Telekom Cloud PostgreSQL DBaaS:
A Shining Star](TODO) on comparing the performance and price-performance of AWS RDS for PostgreSQL, MS Azure Database for PostgreSQL - Flexible Server and OTC RDS PostgreSQL. For more details on the method and the benchmark objectives please refer to the [associated article](https://benchant.com/insights/otc-postgresql-shining-star). 

The performance comparison is based on the following three [BenchBase](https://github.com/cmu-db/benchbase) workloads:
1. analytics: TPC-H
2. telecommunication: TATP

Each folder contains the data of a single run benchmark of one configuration. Each configuration is measured three times.  

***

## Data Set Structure


In order to ensure full transparency and reproducibility,  each data folder contains benchmark configuration data,  performance data, monitoring data, cloud provider metadata, VM metadata and DBMS configuration data.

In addition the `aggregation.xlsx` provides an abstracted view over all data points.  

***

### Benchmark Configuration Data

All configurable benchmark parameters are defined in the `evaluationScenario.json`.

The `benchANT_versions` contains the used versions of the benchANT software components to execute the benchmarks. 

The execution logs of the individual benchmark steps are contained in `airflowTaskInstanceDetails.json`. 

***

### Performance Data

The raw performance data output of the YCSB is contained in the `0_load.txt`  for the LOAD phase and in the `0_run.txt`for the RUN phase. The article only considers the RUN phase. 

In addition, the `runtimeDataframe.xlsx` represents a cleaned time-series of the LOAD and RUN phase performance data. 
 
The `0_tpch_*.csv` and `0_tatp_*.csv` files contain fine grained performance metrics on a per query basis. 

***

### Monitoring Data

The  benchmark instances are monitored with [Telegraf](https://github.com/influxdata/telegraf) and the data is stored in [InfluxDB](https://github.com/influxdata/influxdb). 

A full snapshot of the monitoring data of each run is contained in the  `influx_data.zip` file.



*** 

### Cloud Provider Metadata

The cloud provider metadata for the DBMS deployment is contained in the `dbaas_resources.json`  and for the benchmark deployment in the `benchmark_resources.json`. 


*** 

### VM Metadata

The VM metadata for the  benchmark deployment in the `benchmark_hardware_facts.json`.  


*** 

### DBMS Metadata

For each DBMS, relevant configuration files and cluster states are stored before executing the workload. 

DBMS-specific files are contained in each folder, e.g. `postgresql.conf` for PostgreSQL DBMS deployments. 

*** 


## Contact

In case of questions or feedback on the data feel free to reach out to info@benchant.com

## Disclaimer

Open Telekom Cloud commissioned the work presented in the associated article. Open Telekom Cloud chose the competitors, the test, and the database sizes. benchANT chose the most compatible configurations for the other tested DBaaS, executed the benchmarks and analyzed the results.

