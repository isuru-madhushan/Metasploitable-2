## 25/tcp   open  smtp        Postfix smtpd
## uswer enumaration using SMTP
## using metaspolit framework auxiliary

msf6 > search smtp_enum

Matching Modules
================

   #  Name                              Disclosure Date  Rank    Check  Description
   -  ----                              ---------------  ----    -----  -----------
   0  auxiliary/scanner/smtp/smtp_enum  .                normal  No     SMTP User Enumeration Utility


Interact with a module by name or index. For example info 0, use 0 or use auxiliary/scanner/smtp/smtp_enum

msf6 > use 0
msf6 auxiliary(scanner/smtp/smtp_enum) > show options 

Module options (auxiliary/scanner/smtp/smtp_enum):

   Name       Current Setting                                                Required  Description
   ----       ---------------                                                --------  -----------
   RHOSTS                                                                    yes       The target host(s), see https://docs.metasploit.com/docs/using-metasploit/basics/using-metasploit.html
   RPORT      25                                                             yes       The target port (TCP)
   THREADS    1                                                              yes       The number of concurrent threads (max one per host)
   UNIXONLY   true                                                           yes       Skip Microsoft bannered servers when testing unix users
   USER_FILE  /usr/share/metasploit-framework/data/wordlists/unix_users.txt  yes       The file that contains a list of probable users accounts.


View the full module info with the info, or info -d command.

msf6 auxiliary(scanner/smtp/smtp_enum) > set rhosts 192.168.161.131
rhosts => 192.168.161.131
msf6 auxiliary(scanner/smtp/smtp_enum) > exploit
[*] 192.168.161.131:25    - 192.168.161.131:25 Banner: 220 metasploitable.localdomain ESMTP Postfix (Ubuntu)

#########################################
[+] 192.168.161.131:25    - 192.168.161.131:25 Users found: , backup, bin, daemon, distccd, ftp, games, gnats, irc, libuuid, list, lp, mail, man, mysql, news, nobody, postfix, postgres, postmaster, proxy, service, sshd, sync, sys, syslog, user, uucp, www-data
########################################

[*] 192.168.161.131:25    - Scanned 1 of 1 hosts (100% complete)
[*] Auxiliary module execution completed


verify
#########################################
└─$ nc 192.168.161.131 25
220 metasploitable.localdomain ESMTP Postfix (Ubuntu)
VRFY daemon
252 2.0.0 daemon
VRFY games
252 2.0.0 games

