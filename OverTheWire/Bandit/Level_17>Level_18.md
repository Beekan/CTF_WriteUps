# Level Goal

There are 2 files in the homedirectory: passwords.old and passwords.new. The password for the next level is in passwords.new and is the only line that has been changed between passwords.old and passwords.new

NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19

# Solution 

1. Use ```diff``` to find the difference between the two files.
```Bash
diff passwords.old passwords.new
```
The Correct password in this case is the second one. If passwords.new was written first, the correct password would be written first. The difference is written in the order of the input given.

2. Exit bandit17 shell
```Bash
exit
```

3. ssh into bandit18
```Bash
ssh bandit18@bandit.labs.overthewire.org -p 2220
```
Password: kfBf3eYk5BPBRzwjqutbbfE887SVc5Yd

# Explanation

Just use diff to find the difference, no explanation here. You can see how diff operates if more info is needed.


