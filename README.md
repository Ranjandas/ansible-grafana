ansible-grafana
=========

Role to install Grafana The leading tool for querying and visualizing time series and metrics.

Requirements
------------

You will have to use the ansible `yum_repository` module to setup Grafana YUM repository.

Example:

```
- name: create grafana repo
  yum_repository:
        name: grafana
        description: grafana public repository
        baseurl: https://packagecloud.io/grafana/stable/el/6/{{ ansible_architecture }}
        gpgkey: https://packagecloud.io/gpg.key https://grafanarel.s3.amazonaws.com/RPM-GPG-KEY-grafana
```

Role Variables
--------------

Settable role variables can be found at `defaults/grafana.ini.yml`

Example Playbook
----------------

```
    - hosts: grafana_server
	  tasks:
		- name: create grafana repo
      	  yum_repository: 
				name: grafana
          		description: grafana public repository
          		baseurl: https://packagecloud.io/grafana/stable/el/6/{{ ansible_architecture }}
          		gpgkey: https://packagecloud.io/gpg.key https://grafanarel.s3.amazonaws.com/RPM-GPG-KEY-grafana
      roles:
         - ansible-grafana
```
