# Level Goal

The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.

# Solution

1. Echo the password from the directory given before to local host on port 30000 using ```nc```.
```Bash
echo "$(cat /etc/bandit_pass/bandit14)" | nc localhost 30000
```
The password should be visible now.

(Cautionary step taken in this challenge was checking that the port 30000 was  already open using nmap on the locahost.)

2. Exit bandit14 shell
```Bash
exit
```

3. ssh into bandit15
```Bash
ssh bandit15@bandit.labs.overthewire.org -p 2220
```

Password: BfMYroe26WYalil77FoDi9qh59eK5xNr

# Explanation

The command could be divided into 2 parts. The echo section, and piping the output of the echo section to nc.

1. echo is used here with a small bash script that prints out the contents of the password file.

2. The output of the echo ( which is the password) is then piped to the localhost on port 30000 using nc.



