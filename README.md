# Debian Packer templates

## Boxes description

* OS : Debian 8.7.1 amd64
* 512MB Ram, 2 CPU
* Use French apt sources.list mirror
* French keyboard
* Vagrant ssh key are installed on vagrant and root users
* Kernel backport installed
* Last Docker Engine is installed with `overlay2` storage driver


## Prerequisites

```
$ brew cask install packer vagrant virtualbox ansible
```

## Build vagrant box

```
$ packer build sk-debian-8-jessie.json
```


### Install your new box

```bash
$ vagrant box add sk-debian-8 ./packer_virtualbox-iso_virtualbox.box --force
```

The VM image has been imported to vagrant, it's now available on your system.


## Vagrant

### Getting Started

To use this image with Vagrant, create a vagrant file:

```bash
$ vagrant init sk-debian-8
```


Add this line in `Vagrantfile`:

```
config.vm.synced_folder '.', '/home/vagrant/sync', disabled: true
```


And initialize the vm:

```bash
$ vagrant up
```
