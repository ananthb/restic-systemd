# restic-systemd
Systemd units for backing up to restic repositories on a schedule.

# use

## download
    git clone https://github.com/ananthb/restic-systemd.git
    cd restic-systemd
    
## install units
[restic-backup@.timer](./restic-backup@.timer) will run once a day at midnight, and [restic-prune@.timer](./restic-prune@.timer) will run once a month at midnight.

    sudo cp restic-* /etc/systemd/system/
    sudo systemctl daemon-reload
    sudo mkdir /etc/restic

## create `my-backup` backup job
Repeat these steps to setup multiple backup jobs

    sudo cp config.template /etc/restic/my-backup # edit this file with your config
    sudo systemctl enable restic-backup@my-backup.timer restic-prune@my-backup.timer
