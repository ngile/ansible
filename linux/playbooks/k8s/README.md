# Kubernetes setup using Ansible and Vagrant

## Install the libvirt library, the virt-manager and vagrant, and add the current user to the groups libvirt and KVM

```bash
sudo su
apt-get update && apt-get install \
  libvirt-daemon \
  libvirt-clients \
  virt-manager \
  python3-libvirt \
  vagrant \
  vagrant-libvirt
adduser $(id -un) KVM && adduser $(id -un) libvirt
```

## Bring up k8s machines

```bach
vagrant up --provider=libvirt
```
