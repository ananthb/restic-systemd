# restic-systemd

Systemd units for backing up to restic repositories on a schedule.

## INSTALL

[restic-backup@.timer](./restic-backup@.timer) will run once a day at midnight, and [restic-prune@.timer](./restic-prune@.timer) will run once a month at midnight.

    sudo cp restic-* /etc/systemd/system/
    sudo systemctl daemon-reload
    sudo mkdir /etc/restic

## JOBS

Repeat these steps to setup multiple backup jobs

    sudo cp config.template /etc/restic/my-backup # edit this file with your config
    sudo systemctl enable restic-backup@my-backup.timer restic-prune@my-backup.timer

## LICENSE
Copyright (c) 2021-22 Ananth Bhaskararaman

