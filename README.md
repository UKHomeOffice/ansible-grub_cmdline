grub_cmdline
============

Role which helps to manage Grub command line arguments.


Example
-------

```
---

# Example of how to use the role
- hosts: myhost1
  vars:
    grub_cmdline_add_args:
      - biosdevname=0
      - net.ifnames=0
  roles:
    - grub_cmdline

# Example of configuration with more than one argument of the same name
- hosts: myhost2
  vars:
    grub_cmdline_add_args:
      # Arguments with the same name must be defined as one item
      - console=tty1 console=ttyS1,115200n8r
      - net.ifnames=0
  roles:
    - grub_cmdline
```


Role variables
--------------

List of variables used by the role:

```
# Default list of additional Grub command line arguments
grub_cmdline_add_args: []
# Example:
#grub_cmdline_add_args:
#  - biosdevname=0
#  - net.ifnames=0

# Default list of arguments to remove (for Grub 0.9x)
grub_cmdline_remove_args: []
# Example:
#grub_cmdline_remove_args:
#  - biosdevname=0

# Default path to the Grub 0.9x default config file
grub_cmdline_path1: /boot/grub/grub.conf

# Default path to the Grub2 default config file
grub_cmdline_path2: /etc/default/grub
```

All changes are always applied to all configured kernels.


License
-------

MIT


Author
------

Mark Olliver
