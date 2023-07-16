# README

## Terraform Infrastructure for N01580452

This repository contains Terraform modules for creating and managing a full stack application on Azure, which includes resource groups, network infrastructure, VMs (both Linux and Windows), data disks, load balancer, and a Postgres database.

### Overview of the Modules

1. `rgroup-N01580452`: This module is used for creating the Resource Group in Azure.
2. `network-N01580452`: This module is used for setting up the networking infrastructure which includes VNet, subnet, and security group.
3. `common-N01580452`: This module creates common resources required by the VMs including the Log Analytics workspace and the storage account.
4. `vmlinux-N01580452`: This module deploys multiple Linux VMs and manages their configuration.
5. `vmwindows-N01580452`: This module deploys a Windows VM and manages its configuration.
6. `datadisk-N01580452`: This module manages data disks for the VMs.
7. `loadbalancer-N01580452`: This module sets up a load balancer for the VMs.
8. `database-N01580452`: This module deploys a Postgres database server.

### Pre-requisites

- Terraform 0.13+ installed
- Azure CLI installed and authenticated

### Usage

Update the variable values in the respective module tfvars file as needed and execute the following commands:

```bash
terraform init
terraform plan
terraform apply
```

To destroy the created infrastructure:

```bash
terraform destroy
```

> Note: Ensure that the Azure CLI is authenticated (via `az login`) with the correct account before running the above commands.

### Security

The current configuration deploys a Windows VM with a defined password in plain text. It's recommended to use a secret manager like Azure KeyVault or refer the password from environmental variables or a secret file that's not checked into the version control system.

### Contribution

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

### Disclaimer

This is a sample configuration and should not be used as-is for production workloads. Please ensure all configurations meet your requirements and follow security best practices.
