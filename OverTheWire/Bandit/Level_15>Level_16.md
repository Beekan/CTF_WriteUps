# Level Goal

# Solution

1. Echo the password of the current file to the openssl encrypted port using s_client.

```Bash
echo BfMYroe26WYalil77FoDi9qh59eK5xNr | openssl s_client -connect localhost:30001 -ign_eof
```
The password should be visible now.

2. Exit bandit15 shell.
```Bash
exit
```

3. ssh into bandit16.
```Bash
ssh bandit16@bandit.labs.overthewire.org -p 2220
```
Password: cluFn7wTiGryunymYOu4RcffSxQluehd

# Explanation

The Challenge is the same as before with the only difference being that the port connection is encrypted using openssl. The -ign_eof is used to keep the connection alive after printing the connection arguments. Although this type of connection can be viewed by attackers, it is still secure as the connection is encryptecd at the transport layer.
