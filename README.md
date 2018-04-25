Overview
========

A set of standards for Oasis Source repositories.

Naming
======

* The repository should be named in so-called "snake_case", where each word is
  separated from others by an underscore and names are all lowercase
* Any repository matching a single group to a single role should be named the
  same as the inventory group name that it expects as input. That is, if the
  repository name is "servicename_backend" then its primary play should be
  bounded by `hosts: servicename_backend` as well.
* Some playbooks will expose more than one group, as they are targeting a
  layered approach (e.g. some service running on a VM inside of OpenStack).
  Such playbooks should have appropriately shared group names between related
  playbook sets. For instance, running JBoss in an OpenStack VM and running
  AWX inside an OpenStack VM should share group names for the hosts that are
  being provisioned with OpenStack, although not for the VMs that are being
  provisioned from OpenStack itself.
* Repositories that are for supporting things, such as this documentation,
  should have a mnemonic name prefixed with "meta\_".

Layouts
=======

* There is a standard skeleton project that provides the basic layout for an
  Ansible playbook, vagrant folder, and other supporting documentation. It
  should be followed.
* In general, no roles should be written directly into playbooks here in the
  oasis-origin namespace. If there is need for a new role, it should be
  submitted to [oasis-roles] and kept there for the purpose of shareable and
  reusable roles.

Testing
=======

* All playbooks should pass the standard set of linting and checks that are
  present in the Travis checks
* Additionally, all playbooks should always support all Vagrantfiles that are
  shipped in the repository

[oasis-roles]: https://github.com/oasis-roles
