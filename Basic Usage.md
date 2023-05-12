##  Basic Usage

### All Commands

A complete list of commands can be found by typing.

```
./sdtdserver
```

Below are the most common commands available.

### Running

#### start

```
./sdtdserver start
```

#### stop

```
./sdtdserver stop
```

#### restart

```
./sdtdserver restart
```

#### console

Console allows you to view the live console of a server as it is running and allow you to enter commands; if supported.

```
./sdtdserver console
```

> To exit the console press CTRL+b d. Pressing CTRL+c will terminate the server.

### Updating

#### update

Update checks for any server updates and applies them. The server will update and restart only if required.

```
./sdtdserver update
```

Bypass the check and go straight to SteamCMD update.

```
./sdtdserver force-update
```

#### validate

You can use the SteamCMD [validate](https://docs.linuxgsm.com/commands/validate) option when updating the server.

```
./sdtdserver validate
```

### Debugging

#### Details

You can get all important and useful [details](https://docs.linuxgsm.com/commands/details) about the server such as passwords, ports, config files etc.

```
./sdtdserver details
```

#### Debug

Use debug mode to help you if you are having issues with the server. Debug allows you to see the output of the server directly to your terminal allowing you to diagnose any problems the server might be having.

```
./sdtdserver debug
```

#### Logs

Server logs are available to monitor and diagnose your server. Script, console and game server (if available) logs are created for the server.

```
cd /home/sdtdserver/logs
```

### Backup

Backup will allow you to create a complete tar bzip2 archive of the whole server.

```
./sdtdserver backup
```

### Monitor

LinuxGSM can monitor the game server by checking that the proccess is running and querying it. Should the server go offline LinuxGSM can restart the server and send you an alert. You can use cronjobs to setup monitoring.

```
./sdtdserver monitor
```

### Configure LinuxGSM

For details on how to alter LinuxGSM settings visit [LinuxGSM Config Files](https://docs.linuxgsm.com/configuration/linuxgsm-config) page.

### Documentation

For detailed documentation visit the LinuxGSM [docs](https://docs.linuxgsm.com/).

### Cronjobs

To automate LinuxGSM you can set scheduled tasks using cronjobs, to run any command at any given time. You can edit the crontab using the following.

```
crontab -e
```

Below are the recommended cron tasks.

```
*/5 * * * * /home/sdtdserver/sdtdserver monitor > /dev/null 2>&1
*/30 * * * * /home/sdtdserver/sdtdserver update > /dev/null 2>&1
0 0 * * 0 /home/sdtdserver/sdtdserver update-lgsm > /dev/null 2>&1
```

### Configure LinuxGSM

For details on how to alter LinuxGSM settings visit [LinuxGSM Config Files](https://docs.linuxgsm.com/configuration/linuxgsm-config) page.

### Documentation

For detailed documentation visit the LinuxGSM [docs](https://docs.linuxgsm.com/).