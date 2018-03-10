# Add a KMS server in your WD Cloud (version 2) appliance

Tested on Linux wdmc 3.10.70+ (arm71) WD Cloud appliance<br>
Compiled on the WD Cloud (arm71)<br>

All credit goes to Wind4 @ https://github.com/Wind4/vlmcsd which is a `KMS Emulator in C` <br><br>

### Nuts and bolts
1- KMS server `vlmcsd` is copied into the `/bin` directory <br>
2- `vlmcsd` is then chmodded to be executable <br>
3- A shell script called `kms_start.sh` is created (and chmodded) in `/etc/init.d` (to start service on reboot)<br><br>

### How to Install
From a terminal (putty)<br>
`curl -L meliton.github.io/kms2wdcloud2.sh | sh` <br>


### Some helpful commands
From the pfSense web command prompt<br>
`netstat -an | grep 1688` to check if KMS service is running <br>
`pkill vlmcsd` to kill/stop KMS service <br>
`vlmcsd -h` for a list of options <br>
`vlmcsd -V` for the KMS server version <br>

NOTE: If you stop the service, you'll need to restart the appliance or SSH into the box to restart with `vlmcsd` command. <br>
