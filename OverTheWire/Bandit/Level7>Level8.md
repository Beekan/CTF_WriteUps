# Level Goal
The password for the next level is stored in the file data.txt next to the word millionth

# Solution

1. Run the following command to print the whole line that contains the word millionth
```Bash
strings data.txt | grep millionth
```
The password should be visible now.

2. Exit bandit7 shell
 ```Bash
exit
```

3. ssh into bandit8
```Bash
ssh bandit8@bandit.labs.overthewire.org -p 2220
```
Password: cvX2JJa4CFALtqS87jk27qwqGhBM9plV

# Explanation

The strings command prints out all the strings in the file (who would have thought?). The output is then passed on to grep to print out only the line with the millionth in it. This challenge could be done using ```grep``` with its options or using ```cat```. but I think strings is the most straight forward solution.
