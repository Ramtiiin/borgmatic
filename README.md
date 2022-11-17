### Description

A little container I wrote to automate my [Borgbackup](https://github.com/borgbackup)'s using the
excellent [Borgmatic](https://github.com/witten/borgmatic).

It uses cron to run the backups at a time you can configure in `data/borgmatic.d/crontab.txt`.

### Usage
0. Check your server's time and date to be correct. It's important!
1. Create a copy of .env.template and rename it to .env
2. Change This Parameters:
  - TZ (Time Zone)
  - BORG_PASSPHRASE (Your Borg repository passphrase. Don't worry, we will create it)
  - VOLUME_SOURCE (The directory or file that you want to backup)
  - VOLUME_TARGET (The pat of ypur backup repository)
3. To set your backup timing and configuration, you will need to edit [crontab.txt](data/borgmatic.d/crontab.txt).
To get cronjob easier, you can use https://crontab.guru



If using remote repositories mount your .ssh to /root/.ssh within the container.

#### Set Hooks for Postgres database
Ro get backup form your postgres dbs, edit the hook parameters wrote in /root/Borgmatic-Backup/data/borgmatic.d/config.yaml


