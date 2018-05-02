---
layout: page
title: Get KubeVirt
permalink: /get_kubevirt/
order: 3
---

# Install KubeVirt on a scratch Fedora / CentOS VM  {#install_1}
Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

# KubeVirt on MiniKube {#install_2}
Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

# KubeVirt on an existing Kubernetes cluster {#install_3}

Tools to provision resources, deploy clusters and install KubeVirt. This getting started guide is a link from the link:https://github.com/kubevirt/kubevirt-ansible[kubevirt/kubevirt-ansible] github repository.

## Overview

KubeVirt Ansible consists of a set of Ansible playbooks that deploy fully functional virtual machine management add-on for Kubernetes - KubeVirt. Optionally, a KubeVirt or OpenShift cluster can also be configured.

## Contents

* `automation/`: CI scripts to verify the functionality of playbooks.
* `playbooks/`: Ansible playbooks to provision resources, deploy a cluster and install KubeVirt for various scenarios.
* `roles/`: Roles to use in playbooks.
* `vars/`: Variables to use in playbooks.
* `inventory`: A template for the cluster and nodes configuration.
* `requirements.yml`: A list of required Ansible-Galaxy roles to use in playbooks.
* `stdci.yaml`: A configuration file for CI system.

## Usage

To deploy KubeVirt on an existing OpenShift cluster run the command below. For more information on clusters and other deployment scenarious see [playbooks instructions](./playbooks/README.md).

```
ansible-playbook -i localhost playbooks/kubevirt.yml -e@vars/all.yml
```
>**Note:** Check default variables in [vars/all.yml](./vars/all.yml) and update them if needed.

## Questions ? Help ? Ideas ?

Stop by the [#kubevirt](https://webchat.freenode.net/?channels=kubevirt) chat channel on freenode IRC

## Contributing

Please see the [contributing guidelines](./CONTRIBUTING.md) for information regarding the contribution process.

## Automation & Testing

Please check the [CI automation guidelines](./automation/README.md) for information on playbooks verification.

# Useful Links
- [**KubeVirt**](https://github.com/kubevirt/kubevirt)
- [**OpenShift Ansible**][openshift-ansible-project]
- [**Golang Ansible playbook**](https://github.com/jlund/ansible-go)

[openshift-ansible-project]: https://github.com/openshift/openshift-ansible
