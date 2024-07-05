Hydra is a password cracking tool, it will test every word of a given list until correct password is found

Hydra support many auth system like :
- SSH
- VNC
- FTP
- POP3
- IMAP
- SMTP
- HTTP

Principale command syntax :
`hydra -l username -P wordlist.txt server service`
-l = username
-p = wordlist
server = hostname ip
service = the auth system (ssh, smtp, ftp, ...)

exemple : hydra -l mark -P /usr/share/wordlists/rockyou.txt 10.10.233.146 ssh