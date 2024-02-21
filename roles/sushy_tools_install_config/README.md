Role Name
=========

This role will install and configure sushy-tools and dependencies.

Requirements
------------

None

Role Variables
--------------

bmc_user: Desired user name to use when authenticating with sushy tools
bmc_password: Desired password to use when authenticating with sushy tools

Dependencies
------------

None

Example Playbook
----------------

- name: Install and set up sushy tools
  import_role:
    name: sushy_tools_install_config
  vars:
    bmc_user: "admin"
    bmc_password: "pa$$word"
    

License
-------

BSD
