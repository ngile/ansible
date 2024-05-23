# Kubernetes setup using Ansible and Vagrant

## Install the virtualbox, libvirt, the virt-manager and vagrant, and add the current user to the groups libvirt and KVM

```bash
wget wget https://download.virtualbox.org/virtualbox/7.0.18/virtualbox-7.0_7.0.18-162988~Debian~bookworm_amd64.deb
sudo apt install ./virtualbox-7.0_7.0.18-162988\~Debian\~bookworm_amd64.deb
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

1. Using libvirt

```bash
VAGRANT_VAGRANTFILE=$(pwd)/Vagrantfile.libvirt-clients vagrant up --provider=libvirt
```

2. Using virtualbox

```bach
VAGRANT_VAGRANTFILE=$(pwd)/Vagrantfile.vbox vagrant up --provider=virtualbox
```

or

```bash
VAGRANT_VAGRANTFILE=$(pwd)/Vagrantfile.vbox vagrant up

```
