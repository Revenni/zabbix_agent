revenni.zabbix_agent
=========

Ansible role providing the installation and configuration of Zabbix agent (4.0)

[![Platforms](http://img.shields.io/badge/platforms-ubuntu-lightgrey.svg?style=flat)](#)
[![Licence](https://img.shields.io/badge/Licence-MIT-blue.svg)](https://tldrlegal.com/license/mit-license)

Requirements
------------

* None

Role Variables
--------------

### Generic variables (declared in defaults/main.yml + overridden in vars/main.yml)
* ```zabbix_agent_pid_file``` (/var/run/zabbix/zabbix_agentd.pid) - path to pid file
* ```zabbix_agent_log_file``` (/var/log/zabbix/zabbix_agentd.log) - path to zabbix agent log
* ```zabbix_agent_config_file``` (/etc/zabbix/zabbix_agentd.conf) - config file for zabbix agent
* ```zabbix_agent_include_path``` (/etc/zabbix/zabbix_agent.d/*.conf) - path to userparameter files
* ```zabbix_agent_psk_file``` (/etc/zabbix/zabbix_agentd.psk) - pre shared key file
* ```zabbix_agent_psk_hash``` (kmWCW6jtSSFK7XRuMJct2fVINNL1QTYt) - pre shared keys are an md5 of ansible_fqdn + hash specified here.  Please change this by running ```pwgen -s 32 1```
* ```zabbix_agent_log_size``` (0) - size in MB to rotate log.  0 = use logrotate
* ```zabbix_agent_server_ip``` (127.0.0.1) - ip address of zabbix server
* ```zabbix_agent_server_active_ip``` (127.0.0.1) - ip of zabbix server providing active checks


Dependencies
------------

* None

Example Playbook
----------------

    - hosts: all
      become: true
      roles:
         - { role: revenni.zabbix_agent, tags: zabbix_agent }

License
-------

MIT

Author Information
------------------
* [Vince Hillier](https://revenni.com) | [@email](mailto:vince@revenni.com) | [twitter](https://twitter.com/vincedotca)
