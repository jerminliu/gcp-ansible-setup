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

### Initialize the Cloud SDK

```sh
gloud init
```

### Enable Service Management API

[ENABLE THE API](https://console.cloud.google.com/flows/enableapi?apiid=servicemanagement)

### Get service account key

This initial step is required to obtain the service account JSON key file for further operations without user interaction.

```sh
ansible-playbook init.yml
```

Optionally, accepts tags (e.g. `--tags='key'`):

* **key** to generate service account key only
* **billing** to link project to billing account
