# Level Goal
The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

# Solution

1. Use nmap to search for the desired port.
```Bash
nmap -sC -sV localhost -p31000-32000
```
2. Make a directory in /tmp to save the credentials reported from the port in.
```Bash
mkdir /tmp/bandit16
```
3. Create a file in that directory.
```Bash
touch /tmp/bandit16/sshkey
```

4. The desired port is encrypted using SSL and runs an unkown script, unlike echo in the other ports. Echo the password to this port and save the credentials to the file created above.
```Bash
echo cluFn7wTiGryunymYOu4RcffSxQluehd | openssl s_client -connect localhost:31790 -quiet > /tmp/bandit16/sshkey
```

5. Change the permissions of the file to 600 so that it can be accepted as a credentials file from ssh.
```Bash
chmod 600 /tmp/bandit16/sshkey
```

6. ssh into bandit17 using the credentials file created above.
```Bash
ssh -i /tmp/bandit17/sshkey bandit17@localhost
```

# Explanation

The challenge is similar and builds upon what was learnt before. The Change from the previous challenges is the use of nmap and the permissions of an acceptable credential file. As expected the credentials file should not be available to edit so that it wont be accidently changed or tampered with. The other new thing is the use  of nmap, which is used in this challenge with options ```-sC``` and ```-sV``` which returns the open ports and what are the scripts they run and what versions of software are they running. 
