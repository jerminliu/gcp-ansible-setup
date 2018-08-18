# Google Cloud Platform setup using Ansible

## Prerequisites

* (Windows only) [Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/install-win10) and perform further steps in WSL
* Python 2.7+ or Python 3.5+
* [pip](https://packaging.python.org/guides/installing-using-linux-tools/#installing-pip-setuptools-wheel-with-linux-package-managers)
* [Ansible](https://docs.ansible.com/ansible/2.5/installation_guide/intro_installation.html) 2.6.1+
* [Install and initialize the Cloud SDK](https://cloud.google.com/sdk/docs/quickstarts)

(WSL only) Please run:

```sh
export ANSIBLE_CONFIG=$(pwd)/ansible.cfg
```

## Getting started

### 1. Install Python dependencies

```sh
sudo pip install -r requirements
```

### 2. Initialize the Cloud SDK

To authenticate and create new or select existing project, please run:

```sh
gloud init
```

### 3. Enable Service Management API

Once per project [Enable the API](https://console.cloud.google.com/flows/enableapi?apiid=servicemanagement)

### 4. Initialize project

This initial step are required to obtain the service account JSON key file for further operations without user interaction. Also it ensures the configured project is linked to billing account so other services will be available.

```sh
ansible-playbook init.yml
```

Optionally, accepts tags (e.g. `--tags='key'`):

* **key** to generate service account key only
* **billing** to link project to billing account
* **userdata** to generate config file with required parameters that should be edited prior to creating the resources (`userdata.yml` is ignored in source control)


## Create GKE

```sh
ansible-playbook create_cluster.yml -e @userdata.yml
```