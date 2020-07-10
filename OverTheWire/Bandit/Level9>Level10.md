# Level Goal

The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

# Solution

1. Pass the strings within the data.txt file to the grep command to get the line preceeded with at least 2 '=' signs.
```Bash
strings data.txt | grep ===
```
The password should be visible now.


2. Exit bandit9 shell
```Bash
exit
```

3. ssh into bandit10
```Bash
ssh bandit9@bandit.labs.overthewire.org -p 2220
```
Password: truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk

# Explanation 
This challenge is pretty straight forward and just like the ones before. (Notice that the output from the grep command spells out "the password is truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk").

After searching online for different solutions, I found that meta Charachters could be used with grep to further enhance the searching capability of the grep command.
This could be found [Here](https://medium.com/@theGirlWhoEncrypts/overthewire-bandit-level-9-level-10-5cf4b38b5bad). I really like her solutions and explainations. 
