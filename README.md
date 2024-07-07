# Paper MC systemd scripts

Create a user account named `minecraft`.  This will be the service account for running the server.
```
sudo useradd -m -r minecraft
sudo passwd minecraft
```

Download __Paper__ server from:
<https://papermc.io/software/paper>

Place the server in `/home/minecraft/paper` then rename the __Paper__ server executable file to `server.jar`.

Place the file `minecraft` in `/usr/local/bin` and make sure it has execute permissions by running:
```
chmod +x minecraft
```

Place files `minecraft.service` and `minecraft.socket` in `/etc/systemd/system` then run:
```
systemctl enable minecraft
```

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
