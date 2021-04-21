# Airflow-terraform-cloudinit

Just some scripts to deplioy Apache Airflow using terraform (and cloud_init).

## How to use

- Modify variables.tf:
  - Change cloud_provider to the provider you want to use (google, aws, oracle, alibaba, etc)
  - Select the number of nodes
  - Select the number of workers
  - If you are using an external DB (or a managed DB) put the dbconnection string here.

```
cloud_provider = google
num_nodes = 3
num_workers = 2
dbconnection = postgres://user@host1,host2,host3/database
```

- Execute `terraform plan` to check what's going to happen
- Execute `terraform apply`to deploy inrastructure

The script will output:

- IP (and URL) of the frontend.
