==========================
Nornir Nautobot Extensions
==========================

.. image:: https://img.shields.io/pypi/v/nornir_nautobot_extensions.svg
         :target: https://pypi.python.org/pypi/nornir_nautobot_extensions


Overview
--------

Extensions that enable additional platform support for nornir-nautobot.

nornir-nautobot can be found here: https://github.com/nautobot/nornir-nautobot

Current Extensions
------------------

* Fortinet FortiOS

Usage
-----

You need to specify all of the default dispatchers in your nautobot_config.py, along with the new ones.

Example below, including all the current defaults (see the last line for the new extension):


```
PLUGINS_CONFIG = {
    "nautobot_plugin_nornir": {
        "dispatcher_mapping": {
            "default": "nornir_nautobot.plugins.tasks.dispatcher.default.NautobotNornirDriver",
            "default_netmiko": "nornir_nautobot.plugins.tasks.dispatcher.default.NetmikoNautobotNornirDriver",
            "cisco_asa": "nornir_nautobot.plugins.tasks.dispatcher.cisco_asa.NautobotNornirDriver",
            "cisco_nxos": "nornir_nautobot.plugins.tasks.dispatcher.cisco_nxos.NautobotNornirDriver",
            "cisco_ios": "nornir_nautobot.plugins.tasks.dispatcher.cisco_ios.NautobotNornirDriver",
            "cisco_xr": "nornir_nautobot.plugins.tasks.dispatcher.cisco_xr.NautobotNornirDriver",
            "juniper_junos": "nornir_nautobot.plugins.tasks.dispatcher.juniper_junos.NautobotNornirDriver",
            "arista_eos": "nornir_nautobot.plugins.tasks.dispatcher.arista_eos.NautobotNornirDriver",
            "fortinet": "nornir_nautobot_extensions.plugins.tasks.dispatcher.fortinet.NautobotNornirDriver",
        },
    }
}
```

Be sure to check the latest version of nornir-nautobot to see if the defaults have changed as the dispatcher_mapping values are not merged.

You can find the defaults here: https://github.com/nautobot/nornir-nautobot/blob/58232c3a1ffd1c3d0053102b695662c466ce9f0a/nornir_nautobot/plugins/tasks/dispatcher/__init__.py#L12
