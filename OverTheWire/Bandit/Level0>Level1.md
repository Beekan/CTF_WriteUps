# Level goal
The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

# Solution

1.Read The contents of the file using cat command which contains the password.
```Bash
cat readme
```
You should be able to see the password now from the output of the command.

2.Exit bandit0 shell.
```Bash
exit
```

3.ssh into Bandit1.
```Bash
ssh bandit1@bandit.labs.overthewire.org -p 2220
```
Password: boJ9jbbUNNfktd78OOpsqOltutMc3MY1

# Explaination
 
cat (short for concatenate) is going to be explored over the next levels, but for this example it is used to show the ability of the command to view file contents
