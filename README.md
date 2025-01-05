## Block Youtube DNS

The blockYoutube.sh will create DNS false entries for youtube and it makes youtube inaccessible in your system.  
The addCronJob.sh will add an entry in your crontab, so that every 10 minutes, we keep checking if those lines are there and if not it will add them.
What it means is if you really wanna use youtube you can delete those few lines manually from /etc/hosts and youtube will work until the next 10th minute. (But because the DNS will be cached it might more for a little more longer)
You can manually reset the Chrome's DNS manually by clearing the DNS cache and flusing sockets by going to chrome://net-internals/#dns and chrome://net-internals/#sockets respectively.

You can add the cronjob manually as well, but keep in mind since we are editing the priviliged /etc/hosts, it needs to be called with sudo, so it's better to add this cron job in sudo's crontab with "sudo crontab -e" or running the addCronJob.sh with sudo



### Points to Note:

1.  Edit addCronJob.sh line number 4 with the actual path to your location
2.  Run addCronJob.sh with sudo for the above state reasons
