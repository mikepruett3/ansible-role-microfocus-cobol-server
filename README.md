Ansible Role: Micro Focus Visual COBOL Server
=========

Ansible role to install [Micro Focus Visual COBOL Server](https://www.microfocus.com/en-us/products/visual-cobol/overview) software on Linux Servers.

Requirements
------------

The role does not require anyting to run on RHEL and its derivatives. This role assumes that you have the software package located on a web server somewhere in your environment.

Role Variables
--------------

Available variables are listed below, along with default values ```(see defaults/main.yml)```:

``` yaml
service_user: "service-user"
service_group: "service-group"
service_homedir: "/data/user"
ssh_key_type: "ed25519"
software_url: "http://www.example.org"
package_name: "setup_cobol_server"
```

```service_user``` **(Required)** The username to use for the Service Account.

```service_group``` **(Required)** The group name to use for the Service Account.

```service_homedir``` **(Required)** The path to the homedir for the Service Account user.

```ssh_key_type``` **(Required)** The SSH key type to use when creating the Service Account.

```software_url``` **(Required)** The URL that hosts the Installer package. This should be either **http** or **https**.

```package_name``` **(Required)** The Installer package name.

Role variables can be stored with the hosts.yaml file, or in the main variables file.

Dependencies
------------

Oracle-JDK is required for the software package. (OpenJDK not offically supported, but seems to work for my testing.)

Example Playbook
----------------

``` yaml
    - hosts: servers
      roles:
         - role: mikepruett3.microfocus-cobol-server
           vars:
             service_user: "service-user"
             service_group: "service-group"
             service_homedir: "/data/user"
             ssh_key_type: "ed25519"
             software_url: "http://www.example.org"
             package_name: "setup_cobol_server"
```

License
-------

MIT

Author Information
------------------

Role created by [mikepruett3](https://github.com/mikepruett3) on [Github.com](https://github.com/mikepruett3)
