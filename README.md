Nova novncproxy
=========

OpenStack Nova novncproxy service installation

_Tested on Ubuntu Precise (12.04) and Trusty (14.04)_

Requirements
------------

A RabbitMQ server. See below.

For RHEL/CentOS, RHOSP or RDO repositories are needed.

Role Variables
--------------
### Nova novncproxy (set by this role)

| Name | Default value | Description | Note |
|---  |---  |---  |--- |
| `nova_novncproxy_my_ip` | `{{ ansible_eth0.ipv4.address }}` | Management IP for nova-novncproxy ||
| `nova_novncproxy_vncserver_proxyclient_address` | `{{ my_ip }}` | The address to use to connect to the vnc proxy ||
| `nova_novncproxy_vncserver_proxy_address` | `{{ my_ip }}` | The address to which proxy clients should connect ||
| `nova_novncproxy_base_url` | `"{{ nova_novncproxy_protocol }}://{{ vncserver_proxy_address }}:{{ nova_novncproxy_port }}/vnc_auto.html"` | Desired novncproxy base_url ||

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: console001
      roles:
        - role: openstack-nova_novncproxy

---

A complete Ansible playbook demo, which uses this role, is available on Github (openstack-ansible-galaxy/vagrant-ansible-openstack) <https://github.com/openstack-ansible-galaxy/vagrant-ansible-openstack>

---

Credits
-------
RedHat support implemented by Abel Boldú <abel.boldu@gmx.com>

License
-------

Apache

Author Information
------------------

Davide Guerri - davide.guerri@gmail.com
