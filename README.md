gnome-terminal
=========

Installs and configures gnome-terminal for the user.

Requirements
------------

The following roles are required:

- whalej84.pip

The following collections are required:

- community.general

They can be installed by running `ansible-galaxy collection install $COLLECTION`.

To include this role in your `requirements.yml` file, add the following list item:

```yaml
---
roles:
  - name: whalej84.gnome-terminal
    src: https://github.com/WhaleJ84/ansible-role-gnome-terminal.git
    scm: git

  - name: whalej84.pip
    src: https://github.com/WhaleJ84/ansible-role-pip.git
    scm: git

collections:
  - community.general
```

Example Playbook
----------------

This example playbook shows how I would use this role, with custom variables to suit my needs.

```yaml
---
- hosts: localhost

  roles:
    - role: whalej84.gnome-terminal
      vars:
        dummy_var: "true"
      tags: [ gnome-terminal ]
```

