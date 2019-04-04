# roles/virtualbox/ROADMAP.md

## 2019-04-04 - Completed

### Modified to pass Molecule idempotence testing

```shell
ERROR: Idempotence test failed because of the following tasks:
* [xenial -> 127.0.0.1] => virtualbox : Set value of virtualbox_lastest_available_version variable
* [xenial -> 127.0.0.1] => virtualbox : Extract resource filenames from SHA256SUMS
* [xenial -> 127.0.0.1] => virtualbox : create the file resource_filenames without the '*' preceding each file name
* [xenial -> 127.0.0.1] => virtualbox : Grab index as text file
* [xenial -> 127.0.0.1] => virtualbox : Extract raw package name
* [xenial -> 127.0.0.1] => virtualbox : Extract actual package name
* [xenial] => virtualbox : checking if virtualbox is install
* [xenial] => virtualbox : checking if virtualbox is install

* [bionic -> 127.0.0.1] => virtualbox : Set value of virtualbox_lastest_available_version variable
* [bionic -> 127.0.0.1] => virtualbox : Extract resource filenames from SHA256SUMS
* [bionic -> 127.0.0.1] => virtualbox : create the file resource_filenames without the '*' preceding each file name
* [bionic -> 127.0.0.1] => virtualbox : Grab index as text file
* [bionic -> 127.0.0.1] => virtualbox : Extract raw package name
* [bionic -> 127.0.0.1] => virtualbox : Extract actual package name
* [bionic] => virtualbox : checking if virtualbox is already installed
* [bionic] => virtualbox : checking if virtualbox is install
```

### .ansible-lint 

```shell
skip_list:
- '204'  # Lines should be no longer than 160 chars
- '301'  # Commands should not change things if nothing needs doing
- '303'  # Using command rather than module - sed used in place of template, replace or lineinfile module
- '305'  # Use shell only when shell functionality is required
- '306'  # [306] Shells that use pipes should set the pipefail option
```

* matrix for versions

## To Confirm

* uninstall if upgrade is desired
  * group_vars
    * virtualbox_upgrade: false
    * virtualbox_install: true
    * virtualbox_version: latest-stable
  * host_vars / set_facts on local system?
    * virtualbox_upgrade: true
    * virtualbox_install: false
    * virtualbox_version: latest-stable
* enable latest stable vs latest beta
* is checksum required after copy or performed by copy module?
* virtualbox_action: install, purge, reinstall, upgrade
* virtualbox_actions: install, remove, purge, uprade ? see slack role
* support license keys for multiple Extension Pack versions
* notify operator when new version is available and downloaded and prompt to recover bulk license installation.
* menu / documentation
