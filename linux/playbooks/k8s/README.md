# Kubernetes setup using Ansible and Vagrant

## Install the libvirt library, the virt-manager and vagrant, and add the current user to the groups libvirt and KVM

```bash
sudo apt-get update && sudo apt-get install \
  libvirt-daemon \
  libvirt-clients \
  virt-manager \
  python3-libvirt \
  vagrant \
  vagrant-libvirt
sudo adduser $(id -un) KVM && sudo adduser $(id -un) libvirt
```

## Bring up k8s machines

```bach
vagrant up --provider=libvirt
```
