# Level Goal
To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

# Solution

1. The setuid file is used to run an unprivliged command by esclating the permissions and using the permissions of bandit20 user.
```Bash
./bandit20-do cat /etc/bandit_pass/bandit20
```
The password should be visible now.

2. Exit bandit19 shell.
```Bash
exit
```
3. ssh into bandit20
```Bash
ssh bandit20@bandit.labs.overthewire.org -p 2220
```
Password: GbKksEFF4yrVs6il55v6gwY5aVje5f0j

# Explanation

In depth research of how the setuid file is made is still not done. Nevertheless we still know the fact that the file allows a user to run a command with the privlages of another user by (setting user ID).
