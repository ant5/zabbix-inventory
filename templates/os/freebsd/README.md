## FreeBSD base system specific templates for Zabbix
All templates is for Zabbix agent in active mode (see https://github.com/ant5/zabbix-inventory/templates)

# template_jail_freebsd_active
Minimalistic template for Zabbix agent running inside a jail.
It will trigger alarm _"Lost"_ when there is no connection from agent for more than 1 minute (configurable via ``{$AGENT.TIMEOUT}``).
It also introduce a tag "``container``" with value of a jail hostname.
Very usefull to be used as a least child in Zabbix Service Tree for services that depends (runs inside) on this jail to reveal root problem when jail is down/disappeared/not started.

This template also has "traditional" for OS templates Item/Trigger/Macro for ``AGENT.NODATA_TIMEOUT`` (seems to be used for agent misconfiguration).

# template_freebsd_active

This template was maked by some kind man in the Internet by converting official Zabbix Freebsd Template to an active version. The only change for the file here is introducing "``container``" tag with a value of a system hostname (``{$HOST.HOST}`` to be more precise).
