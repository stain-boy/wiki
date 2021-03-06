CouchPotato - An automatic NZB and torrent downloader for Films
===============================================================

In SSH do the commands described in this FAQ. If you do not know how to SSH into your slot use this FAQ: [SSH basics - Putty](https://www.feralhosting.com/faq/view?question=12)  
  
Your FTP / SFTP / SSH login information can be found on the Slot Details page for the relevant slot. Use this link in your Account Manager to access the relevant slot:  
  
![](https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/slot_detail_link.png)  
  
You login information for the relevant slot will be shown here:  
  
![](https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/slot_detail_ssh.png)  
  

Installation
------------

  
This script will set-up couchpotato and automatically proxypass it for you on Apache and/or nginx, if it is installed and then run it in the background.  
  

    wget -qO ~/install.couchpotato http://git.io/3_iozg && bash ~/install.couchpotato

  
**Important notes:**  
  
**1:** If you get an empty blue screen in your browser press F5 (or CTRL + F5) to reload the page. That is all you should need to do.  
  
**2:** It may take a minute or two for the URL given in the script to work so be patient. Press F5 to reload the URL.  
  
**Run the CouchPotato Wizard**  
  
Visit the URL shown in SSH after the script completes. It will be in this format:  
  

    https://server.feralhosting.com/username/couchpotato

  
**Set a username and password**  
  
![](https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/CouchPotato%20-%20An%20automatic%20NZB%20and%20torrent%20downloader%20for%20Films/1.png)  
  
![](https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/CouchPotato%20-%20An%20automatic%20NZB%20and%20torrent%20downloader%20for%20Films/2.png)  
  
Make sure to set a username and password. This is important, otherwise anyone can get access, and automatically start downloads on your slot.  
  
**Set the directory to download the NZB/torrent to**  
  
  
Under Downloaders, the default option is Black Hole, which will just download the NZB/torrent to a folder. You should set the directory to wherever your client watches.  
  
By default, that should be:  
  

    /media/DiskID/home/username/private/client/watch

  
![](https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/CouchPotato%20-%20An%20automatic%20NZB%20and%20torrent%20downloader%20for%20Films/3.png)  
  
Make sure to replace **client** with whichever client you use, for example, `/private/rtorrent/watch`.  
  
CouchPotato also has support for other clients, such as Transmission, which allows it to interact directly with the client, but information for these isn't be included here.  
  
**6: Complete the rest of the wizard**  
  
Fill in any sites that you are a member of.  
  
![](https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/CouchPotato%20-%20An%20automatic%20NZB%20and%20torrent%20downloader%20for%20Films/4.png)  
  
![](https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/CouchPotato%20-%20An%20automatic%20NZB%20and%20torrent%20downloader%20for%20Films/5.png)  
  
Enabling renaming is optional, and isn't covered in this FAQ.  
  
![](https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/CouchPotato%20-%20An%20automatic%20NZB%20and%20torrent%20downloader%20for%20Films/6.png)  
  
Optional:  
  
![](https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/CouchPotato%20-%20An%20automatic%20NZB%20and%20torrent%20downloader%20for%20Films/7.png)  
  
Click this Green link to finish the wizard:  
  
![](https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/CouchPotato%20-%20An%20automatic%20NZB%20and%20torrent%20downloader%20for%20Films/8.png)  
  
Login to couchpotato and enjoy!  
  
![](https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/CouchPotato%20-%20An%20automatic%20NZB%20and%20torrent%20downloader%20for%20Films/9.png)  
  

Rtorrent RPC:
-------------

  
**Important note:** You must have updated to nginx for this to work. Please see this FAQ: [Updating Apache to nginx](https://www.feralhosting.com/faq/view?question=231)  
  

### Prerequisites:

  
1: You have installed rTorrent/Rutorrent via your Feralhosting Manager for the relevant slot.  
  
2: You have updated to nginx  
  

### Configuring the rTorrent rpc:

  
If you done both of these then you can proceed to use the rTorrent option for the Downloaders.  
  
Navigate to Settings/Downloaders. Once there un-check the Blackhole option:  
  
![](https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/CouchPotato%20-%20An%20automatic%20NZB%20and%20torrent%20downloader%20for%20Films/rpc1.png)  
  
Now select the `rTorrent` checkbox:  
  
![](https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/CouchPotato%20-%20An%20automatic%20NZB%20and%20torrent%20downloader%20for%20Films/rpc2.png)  
  
Fill in the information like this:  
  
Where `username` is your Feral username and `server` is the name of the Feral server your slot is hosted on:  
  
**Host:** `https://server.feralhosting.com/username/rtorrent/rpc`  
**username:** `rutorrent`  
**password:** Is you Rutorrent WebUi password visiable in the Slot Details page for the relevant slot in your Feral Manager  
  
![](https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/CouchPotato%20-%20An%20automatic%20NZB%20and%20torrent%20downloader%20for%20Films/rpc3.png)  
  
The click on Test and you should get a successful connection.  
  

Deluge
------

  
To connect your Deluge daemon you'l need to obtain the daemon's login details using the following commands:  
  
For the host and port (whichshould be specified together in the format `server.feralhosting.com:PORT`)  

    hostname -f
    sed -rn 's/(.*)"daemon_port": (.*),/\2/p' ~/.config/deluge/core.conf

  
For the username and password:  

    whoami
    sed -rn "s/$(whoami):(.*):(.*)/\1/p" ~/.config/deluge/auth

  

Starting and restarting
-----------------------

In order to restart the software the existing process should be killed. If the check below does not display a process number please proceed to step 3. These steps are tailored towards processes started by this FAQ.  
  
1.    Check:  

    pgrep -fu "$(whoami)" "CouchPotato.py"

     
2.    Kill:  

    kill "$(pgrep -fu "$(whoami)" "CouchPotato.py")"

     
3.    Restart:  

    python ~/.couchpotato/CouchPotato.py --daemon

  
**Important note:** You can repeat step 1 after attempting to kill to check if it's been shut down. Give the program at least 10 seconds to shut down at step 2 before trying to restart. If it refuses to exit then you have to force it to quit using this command instead:  
  

    kill -9 "$(pgrep -fu "$(whoami)" "CouchPotato.py")"

  
  

