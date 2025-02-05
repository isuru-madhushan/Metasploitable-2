# Nmap Scan Results

Using this nmap command for detect Prot,Version and Host script

<pre>Sudo nmap -sV -sS -sC A.B.C.D</pre>

## Results
### <pre>PORT     STATE SERVICE     VERSION</pre>
### <pre>21/tcp   open  ftp         vsftpd 2.3.4</pre>
<pre>| ftp-syst:
|   STAT:
| FTP server status:
|      Connected to A.B.C.D
|      Logged in as ftp
|      TYPE: ASCII
|      No session bandwidth limit
|      Session timeout in seconds is 300 
|      Control connection is plain text
|      Data connections will be plain text
|      vsFTPd 2.3.4 - secure, fast, stable
|_End of status
|_ftp-anon: Anonymous FTP login allowed (FTP code 230)</pre>


### <pre>22/tcp   open  ssh         OpenSSH 4.7p1 Debian 8ubuntu1 (protocol 2.0)</pre>
<pre>| ssh-hostkey: 
|   1024 60:0f:cf:e1:c0:5f:6a:74:d6:90:24:fa:c4:d5:6c:cd (DSA)
|_  2048 56:56:24:0f:21:1d:de:a7:2b:ae:61:b1:24:3d:e8:f3 (RSA)</pre>


### <pre>23/tcp   open  telnet      Linux telnetd

### <pre>25/tcp   open  smtp        Postfix smtpd
<pre>| ssl-cert: Subject: commonName=ubuntu804-base.localdomain/organizationName=OCOSA/stateOrProvinceName=There is no such thing outside US/countryName=XX
| Not valid before: 2010-03-17T14:07:45
|_Not valid after:  2010-04-16T14:07:45
|_ssl-date: 2025-02-02T15:56:46+00:00; +3s from scanner time.
|_smtp-commands: metasploitable.localdomain, PIPELINING, SIZE 10240000, VRFY, ETRN, STARTTLS, ENHANCEDSTATUSCODES, 8BITMIME, DSN
| sslv2: 
|   SSLv2 supported
|   ciphers: 
|     SSL2_RC2_128_CBC_WITH_MD5
|     SSL2_RC4_128_WITH_MD5
|     SSL2_DES_64_CBC_WITH_MD5
|     SSL2_RC2_128_CBC_EXPORT40_WITH_MD5
|     SSL2_DES_192_EDE3_CBC_WITH_MD5
|_    SSL2_RC4_128_EXPORT40_WITH_MD5</pre>


### <pre>53/tcp   open  domain      ISC BIND 9.4.2
<pre>| dns-nsid: 
|_  bind.version: 9.4.2</pre>


### <pre>80/tcp   open  http        Apache httpd 2.2.8 ((Ubuntu) DAV/2)
<pre>|_http-server-header: Apache/2.2.8 (Ubuntu) DAV/2
|_http-title: Metasploitable2 - Linux</pre>


### <pre>111/tcp  open  rpcbind     2 (RPC #100000)
<pre>| rpcinfo: 
|   program version    port/proto  service
|   100000  2            111/tcp   rpcbind
|   100000  2            111/udp   rpcbind
|   100003  2,3,4       2049/tcp   nfs
|   100003  2,3,4       2049/udp   nfs
|   100005  1,2,3      35260/tcp   mountd
|   100005  1,2,3      35988/udp   mountd
|   100021  1,3,4      37640/udp   nlockmgr
|   100021  1,3,4      57766/tcp   nlockmgr
|   100024  1          47192/udp   status
|_  100024  1          50327/tcp   status</pre>


### <pre>139/tcp  open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)


### <pre>445/tcp  open  netbios-ssn Samba smbd 3.0.20-Debian (workgroup: WORKGROUP)


### <pre>512/tcp  open  exec        netkit-rsh rexecd


### <pre>513/tcp  open  login       OpenBSD or Solaris rlogind


### <pre>514/tcp  open  tcpwrapped


### <pre>1099/tcp open  java-rmi    GNU Classpath grmiregistry


### <pre>1524/tcp open  bindshell   Metasploitable root shell


### <pre>2049/tcp open  nfs         2-4 (RPC #100003)


### <pre>2121/tcp open  ftp         ProFTPD 1.3.1


### <pre>3306/tcp open  mysql       MySQL 5.0.51a-3ubuntu5
<pre>| mysql-info: 
|   Protocol: 10
|   Version: 5.0.51a-3ubuntu5
|   Thread ID: 8
|   Capabilities flags: 43564
|   Some Capabilities: Support41Auth, ConnectWithDatabase, SupportsTransactions, SwitchToSSLAfterHandshake, SupportsCompression, Speaks41ProtocolNew, LongColumnFlag
|   Status: Autocommit
|_  Salt: QnWHCUblw209oCAZ$@Xw</pre>


### <pre>5432/tcp open  postgresql  PostgreSQL DB 8.3.0 - 8.3.7
<pre>|_ssl-date: 2025-02-02T15:56:46+00:00; +3s from scanner time.
| ssl-cert: Subject: commonName=ubuntu804-base.localdomain/organizationName=OCOSA/stateOrProvinceName=There is no such thing outside US/countryName=XX
| Not valid before: 2010-03-17T14:07:45
|_Not valid after:  2010-04-16T14:07:45</pre>


### <pre>5900/tcp open  vnc         VNC (protocol 3.3)
<pre>| vnc-info: 
|   Protocol version: 3.3
|   Security types: 
|_    VNC Authentication (2)</pre>


### <pre>6000/tcp open  X11         (access denied)


### <pre>6667/tcp open  irc         UnrealIRCd


### <pre>8009/tcp open  ajp13       Apache Jserv (Protocol v1.3)
<pre>|_ajp-methods: Failed to get a valid response for the OPTION request</pre>


### <pre>8180/tcp open  http        Apache Tomcat/Coyote JSP engine 1.1
<pre>|_http-title: Apache Tomcat/5.5
|_http-server-header: Apache-Coyote/1.1
|_http-favicon: Apache Tomcat
Service Info: Hosts:  metasploitable.localdomain, irc.Metasploitable.LAN; OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel</pre>


### <pre>Host script results:
<pre>| smb-security-mode: 
|   account_used: <blank>
|   authentication_level: user
|   challenge_response: supported
|_  message_signing: disabled (dangerous, but default)
|_clock-skew: mean: 1h15m03s, deviation: 2h30m00s, median: 2s
|_nbstat: NetBIOS name: METASPLOITABLE, NetBIOS user: <unknown>, NetBIOS MAC: <unknown> (unknown)
|_smb2-time: Protocol negotiation failed (SMB2)
| smb-os-discovery: 
|   OS: Unix (Samba 3.0.20-Debian)
|   Computer name: metasploitable
|   NetBIOS computer name: 
|   Domain name: localdomain
|   FQDN: metasploitable.localdomain
|_  System time: 2025-02-02T10:56:38-05:00</pre>






