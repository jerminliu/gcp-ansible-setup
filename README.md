# Google Cloud Platform setup using Ansible

## Prerequisites

* (Windows only) [Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/install-win10) and perform further steps in WSL
* Python 2.7+ or Python 3.5+
* [pip](https://packaging.python.org/guides/installing-using-linux-tools/#installing-pip-setuptools-wheel-with-linux-package-managers)
* [Ansible](https://docs.ansible.com/ansible/2.5/installation_guide/intro_installation.html) 2.6.1+
* [Install and initialize Cloud SDK](https://cloud.google.com/sdk/docs/quickstarts)

## Set up an environment

```sh
ansible-playbook set-environment.yml
```
