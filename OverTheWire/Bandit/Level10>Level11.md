# Level Goal

The password for the next level is stored in the file data.txt, which contains base64 encoded data

# Solution

1. Decode the file using the base64 command.
```Bash
base64 --decode data.txt
```
The password should be visible now.


2. Exit bandit10 shell
```Bash
exit
```

3. ssh into bandit11
```Bash
ssh bandit11@bandit.labs.overthewire.org -p 2220
```
Password: IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR

# Explanation

The usage of base64 is just a conversion to a different numbering system by converting the binary of ASCII to base64.
