# Level Goal
The password for the next level is stored in a file readme in the homedirectory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.

# Solution

1. ssh into bandit18 and disable the psuedo-terminal allocation so that it wont run the bashrc. file.
```Bash
ssh bandit18@bandit.labs.overthewire.org -p 2220 -T
```
Password: kfBf3eYk5BPBRzwjqutbbfE887SVc5Yd

2. The command line seen is not the normal shell we are as there is not path seen at the start of the command line. Nevertheless this can be used as the normal shell and execute all the commands as normal. First check what are the files that we found in the directory that we logged into.
```Bash
ls
```

3. We get the output "readme". Print out the contents of the file to get the password.
```Bash
cat readme
```
The password should be visible now.

4. Exit bandit18 shell.
```Bash
exit
```
5. ssh into bandit19
```Bash
ssh bandit19@bandit.labs.overthewire.org -p 2220
```
Password: IueksS7Ubh8G3DCwVzrTd8rAVOwq3M5x
## Alternative solution

To get the password the cat command could be executed from the ssh directly.
```Bash
ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme
```
