# gamedig

​[GameDig](https://github.com/sonicsnes/node-gamedig) is a tool that queries game servers and returns outputs data from a query into json format. It can not only check if the game server is online but also return various data such as current maps and players. This allows `./gameserver details` to display live information.

GameDig super-seeds gsquery as the tool to monitor game servers. GameDig is currently optional but recommended and gsquery is kept to ensure compatibility as gamedig requires Node.js to be installed.

## Install Node.js[](https://docs.linuxgsm.com/requirements/gamedig#install-node.js)

GameDig requires [Node.js](https://nodejs.org/) a JavaScript runtime environment installed to work. Use the following instructions to install Node.js.

### Remove existing NodeJS[](https://docs.linuxgsm.com/requirements/gamedig#remove-existing-nodejs)

If you already have an older version of nodejs installed or be having issues with node dependencies. It may be worth reinstalling Node.js.

#### Ubuntu/Debian[](https://docs.linuxgsm.com/requirements/gamedig#ubuntu-debian)

```bash
sudo apt remove --purge nodejs npm
```

```bash
sudo apt clean
```

```bash
sudo apt autoclean
```

```bash
sudo apt install -f
```

```bash
sudo apt autoremove
```

### Install NodeJS[](https://docs.linuxgsm.com/requirements/gamedig#install-nodejs)

Installing nodejs can be problematic, however, using the below should work well.

#### Ubuntu/Debian[](https://docs.linuxgsm.com/requirements/gamedig#ubuntu-debian-1)

```bash
curl -fsSL https://deb.nodesource.com/setup_16.x | sudo -E bash -
```

```bash
sudo apt update && sudo apt install -y nodejs
```

### Install GameDig npm[](https://docs.linuxgsm.com/requirements/gamedig#install-gamedig-npm)

Once nodejs is installed use npm to install gamedig with the following command.

```bash
npm install gamedig -g
```
## Update GameDig[](https://docs.linuxgsm.com/requirements/gamedig#update-gamedig)

Updates to GameDig are regularly made. It is possible to update by running the npm update command.

```bash
npm update -g
```

You can also see which version of gamedig is installed by running the following.

```bash
npm list -g gamedig
```

## Sample output[](https://docs.linuxgsm.com/requirements/gamedig#sample-output)

### Details[](https://docs.linuxgsm.com/requirements/gamedig#details)

Extra info becomes available for game server details.

```
Players: 0/8

Current Map: Outpost
```

## Raw output[](https://docs.linuxgsm.com/requirements/gamedig#raw-output)

```bash
gamedig --type "protocol-valve" --host "1.2.3.4" --port "27015"
```

```
{

"name": "LinuxGSM Server",

"map": "StationKappa",

"password": false,

"raw": {

"protocol": 17,

"folder": "StickyBots",

"game": "StickyBots",

"steamappid": 0,

"numplayers": 0,

"numbots": 0,

"listentype": "d",

"environment": "l",

"secure": 0,

"version": "0.0.6.22",

"port": 7777,

"steamid": "90122418420694019",

"tags": "BUILDID:622,OWNINGID:90122418420694019,OWNINGNAME:LinuxGSM Server,P2PADDR:90122418420694019,P2PPORT:7777,SESSIONFLAGS:171",

"gameid": "889400",

"rules": {

"BUILDID_i": "622",

"NP_i": "0",

"OWNINGID": "90122418420694019",

"OWNINGNAME": "LinuxGSM Server",

"P2PADDR": "90122418420694019",

"P2PPORT": "7777",

"SESSIONFLAGS": "171",

"SN_s": "LinuxGSM Server"

}

},

"maxplayers": 8,

"players": [],

"bots": [],

"query": {

"host": "1.2.3.4",

"address": "1.2.3.4",

"port": 27015,

"port_query": 27015,

"type": "protocol-valve",

"duration": 90,

"attempts": 1

}

}
```