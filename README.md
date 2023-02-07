# Babylon sample deployment guide

User guide to build your own Babylon deployment working dir

## Requirement

- Operating System in [Debian 10, Debian in Wsl 2]
- docker (running)
- az cli :  install [azure cli](https://learn.microsoft.com/fr-fr/cli/azure/install-azure-cli) to authenticate anc access to azure resources.
- git cli
- python3

## Babylon installation

Install Babylon via pip

```bash
# Clone babylon repository
git clone https://github.com/Cosmo-Tech/Babylon.git
# Create Python 3 virtual environnement
cd Babylon
python3 -m venv .venv
# Active Python environnement
source .venv/bin/activate
# Install Babylon and his dependencies
pip install .
# Test babylon commad
cd ..
```

## Babylon directory configuration

Clone this repository and rename it as you want in this guide we'ill use `babylon_repo`


```bash
# syntax git clone https://github.com/Cosmo-Tech/babylon-sample-working-dir.git repository_dir_name
git clone https://github.com/Cosmo-Tech/babylon-sample-working-dir.git babylon_repo
```

Set babylon environment variable witch will be used babylon

- Babylon working directory path witch host all files used by babylon as API files, Kusto scripts ...

```bash
# Edit before run
export BABYLON_WORKING_DIRECTORY=. #to babylon_repo
```

- Babylon config directory witch host host babylon config files as platform.yaml and deploy.yaml

```bash
# Edit before run
export BABYLON_CONFIG_DIRECTORY=./config #to babylon_repo/config
```

## Babylon platform minimal configuration

```yaml
# ~/...path to babylon_repo/config/platforms/platform.yaml

# Set api_url : the url of the API
api_url: ""
# Set api_scope : the default scope used by the API
api_scope: ""
# Set your azure_subscription : The azure subscription used to contain the platform
# You can run `az account subscription list | grep -C 1 cosmotech` to display your azure subscription
azure_subscription: ""
# Set cluster_name: The name of the Azure Data Explorer Cluster used on the platform
cluster_name: ""
# resource_group_name: The name fo the resource group used on the platform
resource_group_name: ""
# ACR source registry name source_registry.azurecr.io
acr_src_registry_name: ""
# ACR destination registry name dest_registry.azurecr.io
acr_dest_registry_name: ""
# Set resources_location: azure resource location ex: westeurope
resources_location: ""
# Storage account name
storage_account_name: ""
```

## Babylon deploy configuration file

```yaml
# ~/...path to babylon_repo/config/deployments/deploy.yaml

# Set organization_id : the id of the organization on the API if you are using an existing organization
organization_id: ""
# Set api_url : the url of the API (used for validation)
api_url: ""
# Set simulator_repository: the solution simulator repository (repository value in Solution.yaml)
simulator_repository: ""
# Set simulator_version: the solution simulator version (version value in Solution.yaml)
simulator_version: ""
# Set simulator_url:the solution simulator url (url value in Solution.yaml)
simulator_url: ""
```

## Terraform cloud file

```yaml
# ~/...path to babylon_repo/terraform_cloud.yaml

# Set token : API token to connect to terraform cloud API
# can be created in this page : https://app.terraform.io/app/settings/tokens
token: "SECURITY_TOKEN"
# Set url : URL of the API for terraform cloud
url: https://app.terraform.io
# Set organization : organization to use on terraform cloud
organization: "ORGANIZATION"
```

## First commands


- Run `babylon` command to check your babylon installation

```bash
babylon
```

- Display your configuration

```bash
babylon config display
```

- Run your first api command

```bash
babylon api organization get-all -f "id, name"
```
