ironic-delete-dynamic
=====================

Removes nodes from ironic utilizing the os_ironic Ansible module that is
installed by bifrost.

Requirements
------------

This role removes a node from ironic utilizing a uuid variable, which
should be defined at the host level.

Role Variables
--------------

uuid: The UUID value representing the ironic host you wish to delete.

ironic_url: This is the url for the ironic server to connect to.  It is
            presently defaulted to "http://localhost:6385/".

nics: A list of dictionary key-value pairs in the format of a key value
      of 'mac' and the value of the mac address for the node.
      Example::

  [{'mac':'01:02:03:04:05:06'},{'mac':'01:02:03:04:05:07'}]

Dependencies
------------

This role has no direct role dependencies although is expected to be
executed as part of bifrost's test sequence.

Example Playbook
----------------

- hosts: baremetal
  connection: local
  name: "Delete the node"
  become: no
  gather_facts: no
  roles:
    - role: ironic-delete-dynamic

License
-------

Copyright (c) 2015 Hewlett-Packard Development Company, L.P.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

Author Information
------------------

Ironic Developers
