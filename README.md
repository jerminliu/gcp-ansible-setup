# Google Cloud Platform setup using Ansible

## Prerequisites

* (Windows only) [Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/install-win10) and perform further steps in WSL
* Python 2.7+ or Python 3.5+
* [pip](https://packaging.python.org/guides/installing-using-linux-tools/#installing-pip-setuptools-wheel-with-linux-package-managers)
* [Ansible](https://docs.ansible.com/ansible/2.5/installation_guide/intro_installation.html) 2.6.1+
* [Install Cloud SDK](https://cloud.google.com/sdk/docs/quickstarts) and log in to your account.

(WSL only) Please run:

```sh
export export ANSIBLE_CONFIG=$(pwd)/ansible.cfg
```

## Log in to Google Cloud

This initial steps are required to obtain the service account JSON key file
for further operations without user interaction.

To make sure credentials are configured and the project property is set, please run:

```sh
gcloud init
```

Create service account and generate the credentials key file:

```sh
ansible-playbook create_service_account.yml
```