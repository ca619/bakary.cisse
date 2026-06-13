# Exemple de logs de sécurité Linux

## Extrait de logs SSH

```log
Jun 12 02:11:03 srv-web sshd[1842]: Failed password for invalid user admin from 185.243.115.84 port 48932 ssh2
Jun 12 02:11:08 srv-web sshd[1845]: Failed password for invalid user admin from 185.243.115.84 port 48940 ssh2
Jun 12 02:11:14 srv-web sshd[1848]: Failed password for invalid user test from 185.243.115.84 port 48951 ssh2
Jun 12 02:11:21 srv-web sshd[1852]: Failed password for root from 185.243.115.84 port 48966 ssh2
Jun 12 02:11:29 srv-web sshd[1859]: Failed password for root from 185.243.115.84 port 48974 ssh2
Jun 12 02:11:41 srv-web sshd[1863]: Connection closed by authenticating user root 185.243.115.84 port 48988 [preauth]
Jun 12 02:12:02 srv-web sshd[1871]: Accepted password for analyste from 192.168.1.20 port 52214 ssh2
Jun 12 02:12:03 srv-web sshd[1871]: pam_unix(sshd:session): session opened for user analyste(uid=1001) by (uid=0)
Jun 12 02:15:10 srv-web sudo: analyste : TTY=pts/0 ; PWD=/home/analyste ; USER=root ; COMMAND=/usr/bin/cat /var/log/auth.log
Jun 12 02:16:42 srv-web sudo: analyste : TTY=pts/0 ; PWD=/home/analyste ; USER=root ; COMMAND=/usr/bin/ss -tulnp
```
