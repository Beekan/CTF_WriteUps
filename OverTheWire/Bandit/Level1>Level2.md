# Level Goal

The password for the next level is stored in a file called - located in the home directory

# Solution

1. View the name of the file needed to be read using 'ls' command.
2. View the contents of the file using cat which contains the password.
```Bash
cat < -
```
You should be able to see the password now from the output of the command

3. Exit bandit1 shell
```Bash
exit
```

4. ssh to bandit2
```Bash
ssh bandit2@bandit.labs.overthewire.org -p 2220
```
Password:CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9

# Explaination

The only difference between this level and the one before is the file name is a special character. To counter this the '<' option is used which specifies that whatever comes next is a file name.
