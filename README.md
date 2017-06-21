# BTLogin

BTLogin is a simple shell script to automate BT FON logins in a headless environment when a GUI web browser is not available.

To install, copy `bt_login.sh` to a convenient location, edit the `user` and `pass` variables to suit and add it as a cron job.

```
crontab -e

* * * * * bt_login.sh 1>/dev/null 2>&1
```

The above example will run the script every minute to check you're logged in.

The script first checks that you have an internet connection by seeing if it can contact the btopenzone.com login server.  If it can, it also checks you are connected to one of the BT Wifi hotspot SSIDs (I got the list off my mobile phone which uses the BT Wifi app; the app in turn adds all the possible SSIDs to your saved networks.) If all is still OK at  this stage, your current login status is determined.  If you are already logged in, it will exit.  If you are logged out, it will attempt to log you in.  Nothing could be simpler.

It is very conceivable that this script can be used as the basis for other open Wifi hotspots that require you to log in.  If you do modify it in this manner, please consider submitting the resulting script as an extra, ie, `o2_login.sh` or similar. 
