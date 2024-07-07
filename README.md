# Paper MC systemd scripts

Download Paper server from:
<https://papermc.io/software/paper>

Create a user account named `minecraft` and place server in `/home/minecraft/paper`.  This will be the service account for running the server and should *not* have __sudo__ access.

Rename the Paper server executable file to `server.jar`.

Place the file `minecraft.sh` in `/usr/local/bin` and make sure it has execute permissions.

Place files `minecraft.service` and `minecraft.socket` in `/etc/systemd/system` then run `systemctl enable minecraft`

Default memory usage is 4GB, to change edit `minecraft.service` and update the following under `ExecStart` to your desired values:
```
-Xms4096M -Xmx4096M
```

Run commands:
```
minecraft /stop
```

-----

Script is using the Aikar's flags from:
<https://docs.papermc.io/misc/tools/start-script-gen>
