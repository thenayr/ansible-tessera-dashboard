Tessera_dashboard
========

Fully sets up instance of the [Tessera dashboard](https://github.com/urbanairship/tessera) on Ubuntu 12.04.

This role configures Tessera to run on Gunicorn and is proxied through using Nginx.

![screenshot](https://raw.githubusercontent.com/urbanairship/tessera/master/docs/screenshots/color-themes-small.png)

Requirements
------------

Tessera itself requires a graphite server to pull data from.  Check out the [Graphite, statsd, ansible playbook](https://github.com/DandyDev/graphite-statsd-ansible-vagrant) for installing and configuring a graphite/statsd

Role Variables
--------------

This role exposes a few variables for configuring the location of the tessera install as well as variables for the configuration file of Tessera itself

```
tessera_dir: /opt/tessera
tessera_secret_key: "new" 
tessera_default_from_time: '-1h'
tessera_default_theme: 'dark'
tessera_graphite_url: 'http://localhost:8080'
```

Dependencies
------------

Ubuntu 12.04

Example Playbook
-------------------------

## Example
```
# Tessera.yml
---
- hosts: all
  roles:
    - tessera
```

## Example with variables
```
# Tessera.yml
---
- hosts: all
  roles:
  - { role: tessera, tessera_secret_key: 'mynewkey'}
```

License
-------

BSD

Author Information
------------------

Ryan van Niekerk, rvanniekerk@gopro.com
