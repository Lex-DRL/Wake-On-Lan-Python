Wake-On-Lan-Python
==================

wol.py is A small Python 3 script to allow the sending of a WOL Magic packet so that LAN clients can be remotely switched on from another machine on the same subnet. Rather than needing to know the MAC address of the desired machine, the script allows you to specify by hostname, so long as that host is included in the configuration file.

For a quick and lazy way to create the configuration file, see [The Wake On Lan section of my router build documentation](https://www.bentasker.co.uk/documentation/linux/258-usurping-the-bthomehub-with-a-raspberry-pi-part-three-routing-remote-administration-and-utilities#WakeOnLan), or run the command without arguments to create a default config file in `~/.config/bentasker.Wake-On-Lan-Python/wol_config.ini`

This is based on a recipe from http://code.activestate.com/recipes/358449-wake-on-lan/ which was then ameded to use a config file and hostnames.


Usage
-------

    wol.py [-p] [hostname|list]
    
    -p            Prompt for input before exiting
    list          List configured hosts
    [hostname]    hostname to wake (as listed in list)

or

    wol.py list



Configuration File
--------------------

The configuration file is just a basic INI file, containing one section per host;

The configuration file is located at `~/.config/bentasker.Wake-On-Lan-Python/wol_config.ini`

The following is an example of hosts save in `wol_config.ini`

    [General]
    broadcast=192.168.1.255

    [MyPc]
    mac=00:13:0d:e4:60:61



License
--------

Copyright (c) Fadly Tabrani, B Tasker, released under PSF v2, see [LICENSE](LICENSE)
