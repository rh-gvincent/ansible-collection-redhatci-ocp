# Ansible Role: Generate MicroShift ISO

This Ansible role automates the process of generating a MicroShift ISO image.

## Requirements

- Red Hat Subscription Manager (RHSM) for registering the host.
- OCP pull secret for MicroShift

## Role Variables

The role requires the following variables to be defined:

- `microshift_generate_iso_action`: Specifies the action to perform. Default is `"install"`.
- `microshift_generate_iso_folder`: The directory where MicroShift files will be stored. Default is `"/home/{{ ansible_user }}/microshift"`.
- `microshift_generate_iso_folder_blueprints_dir`: The directory within `microshift_generate_iso_folder` where blueprints will be stored. Default is `"{{ microshift_generate_iso_folder }}/blueprints"`.
- `microshift_generate_iso_localhost_folder`: The directory on the localhost where the ISO will be saved. Default is `"/tmp"`.
- `microshift_generate_iso_microshift_version`: The version of Microshift to use. Default is `"4.14"`.
- `microshift_generate_iso_ssh_key`: The SSH public key to use for accessing servers. Default is the content of `~/.ssh/id_rsa.pub`.

## Example Playbook

```yaml
- hosts: microshift_build_server
  roles:
    - role: microshift_generate_iso
