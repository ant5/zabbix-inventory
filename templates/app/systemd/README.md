# template_app_systemd_active_ap
This is a pure conversion of an official **"Systemd by Zabbix agent 2"** template to an active mode. In reckon for future official **active** template the _AP_ suffix to the file/template name was added.

It seems that you also need to Add a loopback interface to the Host to make template working _(it is not an action that open ports on a host)_:

<img width="879" height="428" alt="image" src="https://github.com/user-attachments/assets/a69c4ffc-680d-477b-9938-f6286c524153" />

