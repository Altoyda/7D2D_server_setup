# Server management

## Automatic restarting after shutdown

So you probably want to restart your server in a timed interval. Shutting it down is easy, bringing it back up is the hard part.

### Linux

If you've followed the installation guide in these docs, you will have 7 Days to Die running with LGSM which comes with some very handy management scripts. See [their docs (opens new window)](https://docs.linuxgsm.com/configuration/cronjobs)for a detailed explanation.

However, you may have installed 7 Days to Die in a different way. Fear not, there's options for you aswell!

#### Systemd

[systemd (opens new window)](https://wiki.archlinux.org/index.php/Systemd)in installed on many distros these days. We will use it to turn your server into a service which will automatically handle things like log management, service monitoring, ... for you. Systemd can do **a lot** of things for you and is very customizable, we recommend you read up on it for more info but here is a basic example service file to get you started.

```
[Unit]
Description=7 Days to Die
After=network.target

[Service]
Type=simple
User=sdtd
WorkingDirectory=/home/sdtd
ExecStart=/home/sdtd/startserver.sh -configfile=serverconfig.xml
Restart=on-failure # or always, on-abort, etc

[Install]
WantedBy=multi-user.target
```

#### Script cronjob

This approach is basic but it gets the job done.

```
#!/bin/sh
SERVICE='7DaysToDieServer'

if ps ef | grep -v grep | grep $SERVICE > /dev/null
then
echo "$SERVICE service running, everything is fine"
else
echo "$SERVICE is not running"
nohup /home/sdtd/7d2d/startserver.sh -configfile=serverconfig.xml &
fi
```

_Credit to Highhope for this script_