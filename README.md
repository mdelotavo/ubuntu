Generate ssh keys.
```sh
$ ssh-keygen
```

Add public key to `authorized_keys`.
```sh
$ cat ~/.ssh/id_rsa.pub >> authorized_keys
```

Build image.
```sh
$ docker build -t mdelotavo/ubuntu .
```

Run container.
```sh
$ docker run -d -P --name ubuntu mdelotavo/ubuntu
```

Find port.
```sh
$ docker port ubuntu 22
0.0.0.0:32769
```

Connect to port.
```sh
$ ssh root@localhost -p 32769
The authenticity of host '[localhost]:32769 ([::1]:32769)' can't be established.
ECDSA key fingerprint is SHA256:YDeguQpcdx30uDvK3olLXLQ55ol3uFcox1XLIoxjerA.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added '[localhost]:32769' (ECDSA) to the list of known hosts.
Welcome to Ubuntu 18.04.1 LTS (GNU/Linux 4.9.125-linuxkit x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage
This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

root@e4b79893c965:~# 
```