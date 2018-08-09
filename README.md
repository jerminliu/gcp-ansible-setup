# Google Cloud Platform setup using Ansible

## Prerequisites

* (Windows only) [Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/install-win10) and perform further steps in WSL
* Python 2.7+ or Python 3.5+
* [pip](https://packaging.python.org/guides/installing-using-linux-tools/#installing-pip-setuptools-wheel-with-linux-package-managers)
* [Ansible](https://docs.ansible.com/ansible/2.5/installation_guide/intro_installation.html) 2.6.1+
* [Install Cloud SDK](https://cloud.google.com/sdk/docs/quickstarts) and log in to your account.

## Log in to Google Cloud

This initial step is required to obtain the service account JSON key file
for further logins without user interaction.

Please run:

```sh
gcloud auth login
```

to obtain new credentials, or if you have already logged in with a
different account:

```sh
gcloud config set account ACCOUNT
```

Initialize a connection to the account which will persist service account JSON key file for further operations.

```sh
ansible-playbook playbook.yml --tags 'init'
```

Manage project

```sh
ansible-playbook playbook.yml --tags 'create_project'
```
