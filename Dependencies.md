##  Dependencies

Before installing, you must ensure you have all the dependencies required to run sdtdserver.

These intructions also cover other RHEL derivatives such as AlmaLinux and Rocky Linux.

#### Ubuntu 64-bit

##### Ubuntu =< 20.04

![Ubuntu Icon](https://linuxgsm.com/wp-content/themes/linuxgsm/img/ubuntu64.png)
```bash
sudo dpkg --add-architecture i386; sudo apt update; sudo apt install curl wget file tar bzip2 gzip unzip bsdmainutils python3 util-linux ca-certificates binutils bc jq tmux netcat lib32gcc1 lib32stdc++6 libsdl2-2.0-0:i386 steamcmd telnet expect
```

##### Ubuntu => 20.10

![Ubuntu Icon](https://linuxgsm.com/wp-content/themes/linuxgsm/img/ubuntu64.png)

```bash
sudo dpkg --add-architecture i386; sudo apt update; sudo apt install curl wget file tar bzip2 gzip unzip bsdmainutils python3 util-linux ca-certificates binutils bc jq tmux netcat lib32gcc-s1 lib32stdc++6 libsdl2-2.0-0:i386 steamcmd telnet expect
```
##  Gamedig

GameDig is a recommended additional module that allows LinuxGSM to gather more info from the game server such as current map and connected players to be displayed in details and in logs. It also replaces the default LinuxGSM query module in monitor. To install GameDig follow the steps in the LinuxGSM [documentation](https://docs.linuxgsm.com/requirements/gamedig).

##  Install Dependencies Using LinuxGSM

It is possible for LinuxGSM to install dependencies either by having the sdtdserver user account with sudo access or running the installer as root.

### user with sudo access

During the installation if the game server user has sudo permissions LinuxGSM will attempt to install any missing dependencies itself.

### root user

if sdtdserver is already installed run `./sdtdserver install` as root and LinuxGSM will automatically install missing dependencies.