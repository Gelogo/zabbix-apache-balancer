Dunno if it's due to my lack of knowledge but there is nothing that integrates completely between Zabbix and the apache balancer module, so this template was born, which calls the classic balancer-manager page and interprets the present table.

This works with Zabbix agent and localhost/127.0.0.1 requests. Everything is configured inside the template.
On the apache side, just allow manager page from local:
```
        <Location /balancer-manager>
                SetHandler balancer-manager
                Order Allow,Deny
                ...
                Allow from 127.0.0.1
                ...
        </Location>
```
