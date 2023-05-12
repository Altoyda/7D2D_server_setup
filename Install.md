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