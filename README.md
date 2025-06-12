Ansible Role - Arduino Patch Platform
=========

Removes -w from platform.txt in Arduino cores

Requirements
------------

Arduino have to be present

Role Variables
--------------

`arduino_platform_root`: Root directory to search for platform.txt files (default: `{{ lookup('env', 'HOME') }}/Library/Arduino15/packages`)

`arduino_platform_glob`: Pattern for platform.txt files to patch (default: `{{ arduino_platform_root }}/**/platform.txt`)

`arduino_patch_mode`: Patch or restore platform.txt files (default: `patch`)

Dependencies
------------

Arduino. At least the directory must exist.

Example Playbook
----------------
### Minimum
```
- hosts: localhost
  gather_facts: yes
  roles:
    - role: arduino-patch-platform
```
### Custom Path
```
- hosts: localhost
  gather_facts: yes
  roles:
    - role: arduino-patch-platform
      vars:
        arduino_platform_root: "/custom/path/to/platforms"
```
### Patch Mode (default)
```
- hosts: localhost
  gather_facts: yes
  roles:
    - role: arduino-patch-platform
      vars:
        arduino_patch_mode: patch
```
### Restore Mode
```
- hosts: localhost
  gather_facts: yes
  roles:
    - role: arduino-patch-platform
      vars:
        arduino_patch_mode: restore
```

License
-------

MIT

Author Information
------------------

Tobias Bildner
