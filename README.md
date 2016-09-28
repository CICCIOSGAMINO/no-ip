#no-ip

Simple script to update the no-ip DDNS service 

Crontabs allows you to specify a schedule to run the script and it will also run the script as the user the crontab is configured for. Make sure that the user has execute permissions on the script, read permissions on the config file, and write permissions to the log file. Crontabs will run the script on a scheduled basis so there is no need to specify an interval.

Here’s how to run the script as root.

_1. Create a folder in etc.

    sudo mkdir /etc/no-ip
    
_2. Create a config file.

    sudo touch /etc/no-ip/no-ip.conf
    
_3. Set the parameters with your favorite editor. I use nano. See the Config File section above for details.
