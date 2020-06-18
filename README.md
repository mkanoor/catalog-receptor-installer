Catalog Receptor Installer
============================

A role for setting up system which would allow an on premise Ansible Tower to connect to cloud.redhat.com. It installs the receptor and catalog plugin and registers the Ansible Tower as a valid Source in cloud.redhat.com.

Requirements
------------

This role requires a RHEL system which is registered with the Red Hat Subscription Manager (RHSM).
If the system is not registered and if you provide RHN credentials it will register the system

This role requires that the user is an org admin so that we can automatically
add the sources into cloud.redhat.com

This role will install the python packages for receptor and the catalog plugin from registered repos.

Role Variables
--------------

* `rhn_user` - The RHN user to use if the system is not registered 
* `rhn_password` - The RHN password to use if the system is not registered 
* `tower_url` - The base URL for the Ansible Tower API
* `tower_user` - The user to connect to the Ansible Tower API with
* `tower_password` - The password to authenticate against the  Ansible Tower API with
* `tower_ca_file` - The path to the CA file to validate Tower's certificate (default: `/etc/pki/tls/certs/ca-bundle.crt`)
* `tower_validate_certs` - Whether to validate the Tower certificate is trusted (default: `yes`)
* `install_receptor_from_rpm` - Whether you want the role to install Receptor and Catalog Plugin for you (default: `yes`)
* `receptor_config_dir` - The path to Receptor's configuration files (default: `/etc/receptor`)
* `receptor_data_dir` - The path to Receptor's data files (default: `/var/data/receptor`)
* `receptor_packages` - The packages required to be installed for Receptor to work (default: `receptor` and `python3-receptor-catalog`)
* `c_rh_c_host` - The API endpoint to connect to for cloud.redhat.com (default: `cloud.redhat.com`)
* `source_display_name` - The name for this Ansible Tower in Sources on cloud.redhat.com (default: the hostname of the `tower_url`)

License
-------

GPLv3

Author Information
------------------

This role is written and maintained by Red Hat.
