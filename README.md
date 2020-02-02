Role Name
=========
Ntp configuration

Role Variables
--------------
- ntp_pkg_state: 'latest'
- ntp_service_state: 'started'
- ntp_service_enabled: 'yes'
- ntp_config_server: [ '0.pool.ntp.org', '1.pool.ntp.org', '2.pool.ntp.org', '3.pool.ntp.org' ]
- ntp_config_restrict:
    - '-4 default kod notrap nomodify nopeer noquery'
    - '-6 default kod notrap nomodify nopeer noquery'
    - '127.0.0.1'
    - '::1'
- ntp_config_listen: []
- ntp_config_filegen:
    - 'loopstats file loopstats type day enable'
    - 'peerstats file peerstats type day enable'
    - 'clockstats file clockstats type day enable'
- ntp_config_statistics: 'loopstats peerstats clockstats'
- ntp_config_crypto: ''
- ntp_config_includefile: ''
- ntp_config_keys: ''
- ntp_config_trustedkey: ''
- ntp_config_requestkey: ''
- ntp_config_controlkey: ''
- ntp_config_broadcast: ''
- ntp_config_broadcastclient: ''
- ntp_config_multicastclient: ''
- ntp_config_tinker_panic_enabled: ''
  
Example Playbook
----------------
    - hosts: all
      roles:
         - { role: AnatomicJC.ntp }

Author Information
------------------
- Jean-Christophe Vassort
