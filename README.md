# awx-job-race

This ansible role get the amount of jobs launched by all users in AWX and put this data in an influxdb.
Is possible to use a grafana for print a dashboard like this
![grafana](grafana_example.png)

### Variable to be set

- inventories/awx_jobs_stats/all_vars.yml

```yaml
influxdb_ip_address: "http://<INFLUXDB_HOSTNAME>:8086"
influxdb_database_name: "awx_job_race"
awx_hostname: "<AWX_HOSTNAME>"
```

- inventories/awx_jobs_stats/all_vault.yml

```yaml
awx_user: "admin"
awx_pass: "password"
```

### Use

```bash
ansible-playbook --ask-vault-pass --tags=stats main.yml
```

