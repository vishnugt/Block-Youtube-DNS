## Block Youtube DNS

- The blockYoutube.sh will create false DNS entries for Youtube and it makes youtube inaccessible in your system.  <br> 
- The addCronJob.sh will add an entry in your crontab, so that every 10 minutes, we keep checking if those lines are there in /etc/hosts and if not, the script will add them.<br>
- What it means is, if you really wanna use youtube you can delete those few lines manually from /etc/hosts and youtube will work until the next 10th minute. (But because the DNS is cached, it might work more for a little more longer) <br>
- You can manually reset the Chrome's DNS manually by clearing the DNS cache and flusing sockets by going to chrome://net-internals/#dns and chrome://net-internals/#sockets respectively. Some more context on why this step is only when needed when reverting - https://superuser.com/questions/203674/how-to-clear-flush-the-dns-cache-in-google-chrome#comment207196_203702) <br>
- You can add the cronjob manually as well, but keep in mind since we are editing the priviliged /etc/hosts file, it needs to be called with sudo, so it's better to add this cron job in sudo's crontab with "sudo crontab -e" or by running the addCronJob.sh with sudo <br>



### Points to Note:

1.  Edit addCronJob.sh line number 4 with the actual path to your location
2.  Run addCronJob.sh with sudo for the above stated reasons
