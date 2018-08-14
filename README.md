# Banners

Manage **/etc/motd**, **/etc/issue** and **/etc/issue.net**

# Requirements

To display the **ISSUE** file you have to set `Banner /etc/issue.net` in ssh server configuration file.

# Role Variables

All variables are defined in `defaults/main.yml`

## Global

- `banner_prefix`: path prefix, where to  look for templates. Defaults is the role template, to customize set it to something like `{{ playbook_dir }}/files/banners`
- `banner_updated`: should be the last updated date show?

## ISSUE

- `banner_issue`: should be the **/etc/issue** and **/etc/issue.net** files pressed?
- `banner_issue_files`: list of files for **issue**
- `banner_issue_template`: name of the template file

## MOTD

- `banner_motd`: should be the **/etc/motd** file pressed?
- `banner_motd_files`: list of files for **issue**
- `banner_motd_template`: name of the template file


# Dependencies

None

# Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: hudecof.banners }

## Default ISSUE file
```
********************************************************************
*                                                                  *
* This system is for the use of authorized users only.  Usage of   *
* this system may be monitored and recorded by system personnel.   *
*                                                                  *
* Anyone using this system expressly consents to such monitoring   *
* and is advised that if such monitoring reveals possible          *
* evidence of criminal activity, system personnel may provide the  *
* evidence from such monitoring to law enforcement officials.      *
*                                                                  *
********************************************************************

```

## Default MOTD file
```
**********************************************************************
Hostname:             server
Distribution:         Debian stretch (9.3)

Processors:       1
Memory Installed: 0.5GB
Memory Swapfile:  1.0GB
Mounts:
  Mount: /dev/sda1 (/) (7.7GB)

IPv4 default address:	192.168.93.109 (eth0)

Kernel:              4.9.0-4-amd64
Virtualization Role: guest
Virtualization Type: kvm

******************************** 2017-12-18 15:23:57.595459 **********
```

# License

BSD

# Author Information

Peter Hudec