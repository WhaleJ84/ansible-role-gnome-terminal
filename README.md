gnome-terminal
=========

Installs and configures gnome-terminal for the user.

Requirements
------------

The following roles are required:

- whalej84.psutil

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

  - name: whalej84.psutil
    src: https://github.com/WhaleJ84/ansible-role-psutil.git
    scm: git

collections:
  - community.general
```

Role Variables
--------------

| Name | Type | Description | Default |
| ---- | ---- | ----------- | ------- |
| audible\_bell | string | A lowercase boolean value of [true, false] to state whether the terminal should play an audible bell on set occasions | "true" |
| background\_color | string | A hexadecimal value to state what color the background should be | |
| bold\_color | string | A hexadecimal value to state what color bold text should be | |
| cursor\_background\_color | string | A hexadecimal value to state what color the background of the cursor should be | |
| cursor\_foreground\_color | string | A hexadecimal value to state what color the foreground of the cursor should be | |
| foreground\_color | string | A hexadecimal value to state what color the foreground should be | |
| palette | string | An array of sixteen hexadecimal values to state the normal and bright variants of the black, red, green, yellow, blue, magenta, cyan, and white colors of the terminal should be | |
| use\_theme\_colors | string | A lowercase boolean value of [true, false] to state whether the terminal should use system theme colors | "true" |
| cursor\_shape | string | A value of [block, ibeam, underline] to state what shape the cursor should be | "block" |

Example Playbook
----------------

This example playbook shows how I would use this role, with custom variables to suit my needs.

```yaml
---
- hosts: localhost

  roles:
    - role: whalej84.gnome-terminal
      vars:
        audible_bell: "false"
        # Gruvbox colours
        black: "'#FBFBF1F1C7C7'"
        red: "'#CCCC24241D1D'"
        green: "'#989897971A1A'"
        yellow: "'#D7D799992121'"
        blue: "'#454585858888'"
        magenta: "'#B1B162628686'"
        cyan: "'#68689D9D6A6A'"
        white: "'#7C7C6F6F6464'"
        bright_black: "'#929283837474'"
        bright_red: "'#9D9D00000606'"
        bright_green: "'#797974740E0E'"
        bright_yellow: "'#B5B576761414'"
        bright_blue: "'#070766667878'"
        bright_magenta: "'#8F8F3F3F7171'"
        bright_cyan: "'#42427B7B5858'"
        bright_white: "'#3C3C38383636'"
        #
        background_color: "{{ black }}"
        bold_color: "{{ bright_white }}"
        cursor_background_color: "{{ bright_white }}"
        cursor_foreground_color: "{{ black }}"
        foreground_color: "{{ bright_white }}"
        palette: "[{{ black }}, {{ red }}, {{ green }}, {{ yellow }}, {{ blue }}, {{ magenta }}, {{ cyan }}, {{ white }}, {{ bright_black }}, {{ bright_red }}, {{ bright_green }}, {{ bright_yellow }}, {{ bright_blue }}, {{ bright_magenta }}, {{ bright_cyan }}, {{ bright_white }}]"
        use_theme_colors: "false"
        cursor_shape: "ibeam"
      tags: [ gnome-terminal ]
```

