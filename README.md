
## Installation:
1. Create the Directory: `sudo mkdir /etc/infrabuddy`
2. Move infrabuddy executable and config.toml into directory.
3. Give Execute Permissions:`sudo chmod +x /etc/infrabuddy/infrabuddy`
4. Create the Service File: `sudo nano /etc/systemd/system/infrabuddy.service`
5. Paste into Service File: 
```
[Unit]
Description=InfraBuddy Resource Monitor
After=network.target
Wants=network-online.target

[Service]
Restart=no
Type=simple
ExecStart=/etc/infrabuddy/infrabuddy
WorkingDirectory=/etc/infrabuddy

[Install]
WantedBy=multi-user.target
```
5. Enable the Service: `sudo systemctl enable --now infrabuddy`
6. Start the Service: `sudo systemctl start infrabuddy`
