# Level Goal
The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Note: localhost is a hostname that refers to the machine you are working on

# Solution

1. Use ssh identity file option to login into the bandit14 user on the localhost.
```Bash
ssh -i sshkey.private bandit14@localhost
```

2. No next step this time you are now logged into bandit14 user

# Explanation

The ssh is encrypted using a ssh RSA key. A password is normally used as the user cannot normally input the RSA key as a whole to verify their identity. Nevertheless there is still the option to verify one's identity using the ssh private key using the ```-i``` option
