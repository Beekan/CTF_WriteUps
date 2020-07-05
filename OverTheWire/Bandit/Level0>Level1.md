# Level goal
The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

# Solution

1.Read The contents of the file using cat command
```Bash
cat readme
```

2.Exit from the bandit0 shell
```Bash
exit
```

3.Connect to Bandit1
```Bash
ssh bandit1@bandit.labs.overthewire.org -p 2220
```
Password:boJ9jbbUNNfktd78OOpsqOltutMc3MY1

# Explaination
 
cat (short for concatenate) is going to be explored over the next levels, but for this example it is used to show the ability of the command to view file contents
