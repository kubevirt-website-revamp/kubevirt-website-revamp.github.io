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

This demo will deploy [KubeVirt](https://www.kubevirt.io) on an existing
[minikube](https://github.com/kubernetes/minikube/) with Kubernetes 1.9 or
later.

### Deploy KubeVirt

This demo assumes that [minikube](https://github.com/kubernetes/minikube/) is up and running and `kubectl` available on your system. If not, then please take a look at the guide [below](#appendix-deploying-minikube)

With minikube running, you can easily deploy KubeVirt:

```bash
$ export VERSION=v0.4.1
$ kubectl create \
    -f https://github.com/kubevirt/kubevirt/releases/download/$VERSION/kubevirt.yaml
```

> **Note:** The initial deployment to a new minikube instance can take
> a long time, because a number of containers have to be pulled from the
> internet. Use `watch kubectl get --all-namespaces pods` to monitor the progress.

### Install virtctl

> **Note:** This requires `kubectl` from Kubernetes 1.9 or later on the client

An additional binary is provided to get quick access to the serial and graphical ports of a VM, and handle start/stop operations.
The tool is called `virtctl` and can be retrieved from the release page of KubeVirt:

```bash
$ curl -L -o virtctl \
    https://github.com/kubevirt/kubevirt/releases/download/$VERSION/virtctl-$VERSION-linux-amd64
$ chmod +x virtctl
```

### Deploy a VirtualMachine

Once you deployed KubeVirt you are ready to launch a VM:

```bash
# Creating a virtual machine
$ kubectl apply -f https://raw.githubusercontent.com/kubevirt/demo/master/manifests/vm.yaml

# After deployment you can manage VMs using the usual verbs:
$ kubectl get ovms
$ kubectl get ovms -o yaml testvm

# To start an offline VM you can use
$ ./virtctl start testvm
$ kubectl get vms
$ kubectl get vms -o yaml testvm

# To shut it down again
$ ./virtctl stop testvm

# To delete
$ kubectl delete vms testvm
# To create your own
$ kubectl create -f $YOUR_VM_SPEC
```

### Accessing VMs (serial console & spice)

```
# Connect to the serial console
$ ./virtctl console testvm

# Connect to the graphical display
# Note: Requires `remote-viewer` from the `virt-viewer` package.
$ ./virtctl vnc testvm
```

### Next steps

### User Guide

Now that KubeVirt is up an running, you can take a look at the [user guide](https://www.kubevirt.io/user-guide/#/) to understand how you can create and manage your own virtual machines.

## Appendix: Deploying minikube

1. If not installed, install minikube as described [here](https://github.com/kubernetes/minikube/)

   1. Install the [kvm2 driver](https://github.com/kubernetes/minikube/blob/master/docs/drivers.md#kvm2-driver)
   2. Download the [`minikube` binary](https://github.com/kubernetes/minikube/releases)

2. Launch minikube with CNI:

```bash
$ minikube start \
  --vm-driver kvm2 \
  --network-plugin cni
```

3. Install `kubectl` via a package manager or [download](https://kubernetes.io/docs/tasks/tools/install-kubectl/#install-kubectl-binary-via-curl) it




# KubeVirt on an existing Kubernetes cluster {#install_3}
Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
