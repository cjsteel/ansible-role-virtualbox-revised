# roles/virtualbox/ROADMAP.md

## Fresh

* customize lint comments
* matrix for versions

## Old


* make work


  * Virtualbox

    * Assign 2G memory to virtualbox VM's
    * box version support
  * implement
    * virtualbox_version: latest-stable, latest-beta, 5.2.22
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

    * [systemd - file-hierarchy — File system hierarchy overview](https://www.freedesktop.org/software/systemd/man/file-hierarchy.html)
    * [xdg-user-dirs](https://www.freedesktop.org/wiki/Software/xdg-user-dirs/)
    * (https://www.tldp.org/LDP/Linux-Filesystem-Hierarchy/html/opt.html)
    * [XDG Base Directory Specification](https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html)

  ```shell
  ~/bin/local-menu
  ```

  ```shell
  /opt/menu
  /opt/acemenu/...
  /opt/virtualbox/5.2.22/
  ```

```shell
/usr/share/

    Resources shared between multiple packages, such as documentation, man pages, time zone information, fonts and other resources. Usually, the precise location and format of files stored below this directory is subject to specifications that ensure interoperability.
/usr/share/doc/

    Documentation for the operating system or system packages.
```

```
~/.local/bin/
```

Executables that shall appear in the user's         `$PATH` search path. It is recommended not to         place executables in this directory that are not useful for         invocation from a shell; these should be placed in a         subdirectory of `~/.local/lib/` instead.         Care should be taken when placing architecture-dependent         binaries in this place, which might be problematic if the home         directory is shared between multiple hosts with different         architectures.

```
~/.local/lib/
```

Static, private vendor data that is compatible         with all architectures.

```
~/.local/lib/*arch-id*/
```

Location for placing public dynamic libraries.         The architecture identifier to use is defined on [Multiarch         Architecture Specifiers (Tuples)](https://wiki.debian.org/Multiarch/Tuples)         list.

```
~/.local/share/
```

Resources shared between multiple packages,         such as fonts or artwork. Usually, the precise location and         format of files stored below this directory is subject to         specifications that ensure interoperability. If an application         finds `$XDG_DATA_HOME` set, it should use the         directory specified in it instead of this         directory.



* make right

  * Break up tasks files into logical sub tasks.

  * Clean up vars

  * idempotent

* Someday

  * Operator prompt or programmatic bulk license recovery for Extension Pack
  * 
