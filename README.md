Ansible Role RPMFusion
=========

[![Molecule Test](https://github.com/diademiemi/ansible_role_rpmfusion/actions/workflows/molecule.yml/badge.svg)](https://github.com/diademiemi/ansible_role_rpmfusion/actions/workflows/molecule.yml)

This is an Ansible role to add the RPMFusion repositories.

Include more information about rpmfusion in this section.

Requirements
------------
These platforms are supported:
- EL 8 (Tested on Rocky Linux 8)
- EL 9 (Tested on Rocky Linux 9)
- Fedora 38

<!--
- List hardware requirements here  
-->

Role Variables
--------------

Variable | Default | Description
--- | --- | ---
`rpmfusion_free_repository` | `true` | Indicates whether the RPM Fusion free repository is enabled. Defaults to `true`.
`rpmfusion_nonfree_repository` | `false` | Indicates whether the RPM Fusion nonfree repository is enabled. Defaults to `false`.
`rpmfusion_free_rpm_package_url` | `{{ _rpmfusion_free_rpm_package_url }}` | The URL for RPM packages in the RPM Fusion free repository. Defaults to the value of `_rpmfusion_free_rpm_package_url`.
`rpmfusion_nonfree_rpm_package_url` | `{{ _rpmfusion_nonfree_rpm_package_url }}` | The URL for RPM packages in the RPM Fusion nonfree repository. Defaults to the value of `_rpmfusion_nonfree_rpm_package_url`.
...

See [./vars/](./vars/) for distro-specific variables.

Dependencies
------------
<!-- List dependencies on other roles or criteria -->
None

Example Playbook
----------------

```yaml
- name: Use diademiemi.rpmfusion role
  hosts: "{{ target | default('rpmfusion') }}"
  roles:
    - role: "diademiemi.rpmfusion"
      tags: ['diademiemi', 'rpmfusion', 'setup']    ```

```

License
-------

MIT

Author Information
------------------

- diademiemi (@diademiemi)

Role Testing
------------

This repository comes with Molecule that run in Podman on the supported platforms.
Install Molecule by running

```bash
pip3 install -r requirements.txt
```

Run the tests with

```bash
molecule test
```

These tests are automatically ran by GitHub Actions on push. If the tests are successful, the role is automatically published to Ansible Galaxy.

