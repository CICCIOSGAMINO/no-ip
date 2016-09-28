#no-ip

Simple script to update the no-ip DDNS service 

Crontabs allows you to specify a schedule to run the script and it will also run the script as the user the crontab is configured for. Make sure that the user has execute permissions on the script, read permissions on the config file, and write permissions to the log file. Crontabs will run the script on a scheduled basis so there is no need to specify an interval.

Here’s how to run the script as root.

1. Create a folder in etc.

    sudo mkdir /etc/no-ip
    
2. Create a config file.

    sudo touch /etc/no-ip/no-ip.conf
    
3. Set the parameters with your favorite editor. I use nano. See the Config File section above for details.

    sudo vim /etc/no-ip/no-ip.conf

    user=username 
    password=password 
    hostname=hostname.example.com
    logfile=/var/log/no-ip.log
    detectip=true
    
4. Copy no-ip.sh to /usr/sbin

    sudo cp no-ip.sh /usr/sbin/no-ip.sh
    
5. Make the script executable

    sudo chmod +x /usr/sbin/no-ip.sh
    
6. Logon as root

    sudo -i
    
7. Edit root’s crontab

    crontab -e
    
8. Add the entry to the bottom. 10 tells crontab to run the script evert 10 minutes and save the crontab.

    10 * * * * /usr/sbin/no-up.sh
    
    
That's it, just if you want to be sure restart the cron service : 

    sudo service cron reload 
