##  Install

From the command-line do the following. Ensuring you have also installed the required dependencies.

1. Create a user and login.

```bash
sudo adduser sdtdserver
```

> For security best practice, ensure you set a strong password. Random password: `_jQ1MjU4OTA3N_`

```bash
su - sdtdserver
```

2. Download linuxgsm.sh.

```bash
wget -O linuxgsm.sh https://linuxgsm.sh && chmod +x linuxgsm.sh && bash linuxgsm.sh sdtdserver
```

3. Run the installer following the on-screen instructions.

```bash
./sdtdserver install
```

## First time server start

Remember to login with user **sdtdserver** to perform any action with server (start/stop/update etc.)

Command prompt should looks like **sdtdserver**@server7d:~$ . If you see another username instead of sdtdserver, change active user by issuing command su - sdtdserver

### Switch to X64 version

In some cases, steamcmd cannot recognize you'r have x64 processor and starts x32 version of gameserver. It can lead to memory issues very soon. Dont skip this section!

Enter command as sdtdserver user: 

```bash
nano /home/sdtdserver/lgsm/config-lgsm/sdtdserver/sdtdserver.cfg
```

CFG file will be opened in text editor. It should looks like this

```
##################################
######## Instance Settings ########
##################################
# PLACE INSTANCE SETTINGS HERE
## These settings will apply to a specific instance
```

If you see empty file, exit (press ctrl-x) and double check file name and path!

Carefully edit this file to add 2 lines on the bottom and make it looks like this:

```
##################################
######## Instance Settings ########
##################################
# PLACE INSTANCE SETTINGS HERE
## These settings will apply to a specific instance

executable="/home/sdtdserver/serverfiles/7DaysToDieServer.x86_64"
```