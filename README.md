# roles/virtualbox/README.md

## Status

[![Build Status](https://travis-ci.org/cjsteel/virtualbox.svg?branch=master)](https://travis-ci.org/cjsteel/virtualbox)
[![Travis CI](http://img.shields.io/travis/csteel/virtualbox/default.svg?style=flat)](http://travis-ci.org/csteel/virtualbox/default)
[![Platforms](http://img.shields.io/badge/platforms-debian%20/%20ubuntu-lightgrey.svg?style=flat)](#)

## Description

virtualbox is an Ansible role used to...

## Notes

### Controller resource population

While the role can be used to automatically populate the controller with new releases the bulk installation license for the VirtualBox Extension Pack must still be obtained manually by running something like the following. Once the licence is accepted the bulk license for whatever version you are installing will be displayed along with a new command line usage example with the correct bulk license. This process is a little unfamiliar for first time users.

Enter the following command::

```shell
VBoxManage extpack install --accept-license=22be48f923303c8cababb0bb4c478284b688ed23f16d775d729b89a2e8e5f9ac --replace Oracle_VM_VirtualBox_Extension_Pack-5.2.22.vbox-extpack
```

If you accept the license:

```shell
Do you agree to these license terms and conditions (y/n)? y
```

Something like the following will be displayed:

```shell
License accepted. For batch installaltion add
--accept-license=56be48f923303c8cababb0bb4c478284b688ed23f16d775d729b89a2e8e5f9eb
to the VBoxManage command line.

0%...10%...20%...30%...40%...50%...60%...70%...80%...90%...100%
Successfully installed "Oracle VM VirtualBox Extension Pack".
```

Add the bulk license for the new VirtualBox version's Extention Pack `defaults/main.yml`

## Roadmap

* [ROADMAP.md](ROADMAP.md)

## References

* [docs.ansible.com](https://docs.ansible.com/)

## Requirements

* ansible 2.7 ( reboot module)


### Production

* Ansible

### For Local Testing

* [Vagrant](https://www.vagrantup.com/) - (Tested using version 2.1.1)
* Vagrant plugins:
  * [vagrant-disksize (0.1.2)](https://github.com/sprotheroe/vagrant-disksize)
  * vagrant-vbguest (0.15.2) - Recommended [vagrant-vbguest](https://github.com/cjsteel/vagrant-vbguest)
  * vai (0.9.3) - For testing with multiple vms [vagrant-plugin-vai](https://github.com/cjsteel/vagrant-plugin-vai) 
* [Virtual Box](https://www.virtualbox.org/)
  * Tested using Version 5.2.14 r123301 (Qt5.6.1) 

## Variables

### defaults/main.yml

* [defaults/main.yml](defaults/main.yml) contains all of the required variables.

### project_name/site.yml example

* [example_virtualbox.yml](files/example_site.yml) may contain an example entry.

## Testing

To test with all VM's defined in Vagrantfile run the following:

```shell
cd roles/virtualbox
vagrant up
```

To run on a specific VM's
```shell
vagrant up xenial
```

### VM's tested with Vagrant and Virtualbox

pass, fail, untested

| Distribution | Results  |
| ------------ | -------- |
| precise      | untested |
| trusty       | untested |
| xenial       | untested |
| bionic       | untested |
| CentOS 6     | untested |
| CentOS 7     | untested |

## Authors and License

- [Christopher Steel](http://mcin-cnim.ca/) | [e-mail](mailto:christopher.steel@mcgill.ca)

License: [MIT](https://tldrlegal.com/license/mit-license)


* ansible-role-virtualbox generated using [galaxy-role-skeleton](https://github.com/cjsteel/galaxy-role-skeleton)
