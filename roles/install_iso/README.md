Role Name
=========

This role will install a user specified iso on a target system using sushy-tools.

Requirements
------------

Sushy tools installed and configured on system running this role.  Iso should be available via http.

Role Variables
--------------

Variables which need to be set by the caller of this role:

boot_iso_url: URL of the iso to be installed (ex. http://localhost:80/boot-this-iso.iso
target_host: The name of the VM on which the iso is to be installed (ex. "test_vm")
bmc_address: The machine and port on which sushy tools is running (ex. "localhost:8082")
bmc_user: The user name to use when authenticating with sushy tools (ex. "admin")
bmc_password: The password to use when authenticating with sushy tools (ex. "pa$$word")

Dependencies
------------

None

Example Playbook
----------------

    - name: Install iso on VM
      import_role:
        name: iso_install
      vars:
        boot_iso_url: http://localhost:80/e510c409-f07f-453c-8e05-3322816c8915-installer.iso
        target_host: "my_test_vm"
        bmc_address: "localhost:8082"
        bmc_user: "admin"
        bmc_password: "pa$$word"


License
-------

BSD
