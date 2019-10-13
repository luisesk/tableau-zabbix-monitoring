Tableau Zabbix Monitoring
=========

Role to enable the monitoring of a Tableau Server cluster status throgh Zabbix.
Example Zabbix Template avaiable in the Files directory.

Requirements
------------

Python3
Pip module
  - requests


Role Variables
--------------

tableau_server - IP or DNS of the server wich access the tableau server status page. The rle is usualy placed in the Tableau Cluster controller itself, but it can be placed in a server that has remote access to the Tableau Status XML page. (if locally, try using 127.0.0.1 instead of 'localhost')

status_xml - Path and name of the XML status page file that will be downloaded and stored locally for futher process. This file wil be replaced evey time the script is called and need to be RW by zabbix user.

script_path: - Path that your script will be stored. If the path does not exists, it will be created by ansible as long as the path variable ends with a '/'.

python_path - Path for you python binary, eg.: '/usr/bin/python3'

userparameter_path - path for your userparameters. By default Zabbix uses '/etz/zabbix/zabbix_agentd.d/' but you can use any path as long as it is properly imported in zabbix_agent.conf.


Dependencies
------------

N/A

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: luisesk.tableau-zabbix }

License
-------

MIT

Author Information
------------------

Luis Alberto Paschoal - LuisesK
i9vatech.com
