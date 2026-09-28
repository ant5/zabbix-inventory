## Content description
This repository provide templates for Zabbix monitoring. Zabbix monitoring consist of a Zabbix server, [proxy servers] and agent (thing on a monitored subject).
Templates are tested and used with **Zabbix 7.4**. There is no information how it will work on other versions of Zabbix.

## Prerequisites
This templates work only for Zabbix agents in **active mode**. Active mode (push mode) is when agent connect to a server only by own will and do not open any network ports on a system where they lives.
Agents periodically connect to a server and do some talks (send data, acquire configuration).

Templates for this mode traditionally has an ``active`` suffix in name. Templates whithout ``active`` word may or may not work.

About the Zaabix agent itself. On **FreeBSD** traditional agent is used (``zabbix74-agent``). On **Linux** ``agent2`` is used (due to subjective filling that this choice give a less pain for unifing across different Linux version/distributions).

So, this templates for Zabbix 7.4 with ``agent`` on **FreeBSD** and ``agent2`` on **Linux** each configured for an active mode.

## Configuration
For active mode agent configuration must be something like this.

Agent on FreeBSD, ``/usr/local/etc/zabbix74/zabbix_agentd.conf`` :
```
# force push-only mode
ServerActive=SERVERHOST_OR_IP
Hostname= THISHOST
StartAgents=0


# send interval (in seconds, push every...)
#BufferSend=8
#LogFile=/var/log/zabbix/zabbix_agentd.log
#Include=/usr/local/etc/zabbix74/zabbix_agentd.conf.d/*.conf

```

Agent2 on Linux, (path depends of a Linux distribution) ``/etc/zabbix/zabbix_agent2.conf`` :
```
# force push-only (active) mode
ServerActive=SERVERHOST_OR_IP
Hostname=THISHOST

#LogType=system
#Include=/etc/zabbix/zabbix_agent2.d/plugins.d/postgresql.conf

```
