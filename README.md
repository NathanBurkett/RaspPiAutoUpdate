# RaspPiAutoUpdate
Use a cron daemon to update a raspberry pi everyday at 3am.

## Place the files on your pi
This repository assumes you have the `update` script in `/home/pi/Update`.

## Updating
After booting into the pi via ssh, edit your cron tab with `crontab -e` and add:
```
0 3 * * * /home/pi/Update/update 2>&1 >/home/pi/Update/output.log
```

This command will run the `update` script at 3am local to the raspberry pi system time. Any errors the update process runs into will be output to the `output.log` file in the same folder as the `update` script.
