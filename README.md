# tg_tracker-legacy-
Telegram task tracker

**DAEMON LAUNCHER:**

#!/usr/bin/env bash

#Description: TG TRACKER LAUNCHER

cd ~/path/to/tracker/

python -m venv tgvenv

source ./tgvenv/bin/activate

python3 ./main.py


**DAEMON UNIT:**

[Unit]

Description=TG_TRACKER LEGACY

After=network.target

[Service]

Type=simple

User=root

ExecStart=/path/to/tracker/launcher.sh

Restart=always

[Install]

WantedBy=multi-user.target

**DAEMON INIT**

touch /etc/systemd/system/mydaemon.service

chmod 664 /etc/systemd/system/mydaemon.service

systemctl daemon-reload

systemctl start mydaemon.service

systemctl status mydaemon.service

systemctl enable mydaemon.service
