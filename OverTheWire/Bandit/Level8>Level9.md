# Level Goal

The password for the next level is stored in the file data.txt and is the only line of text that occurs only once.

# Solution

1. Get the strings of the file, sort them, then print out only the uniqe one.
```Bash
strings data.txt | sort | uniq -u
```
The password should be visible now

2. Exit bandit8 shell
```Bash
exit
```

3. ssh into bandit9
```Bash
ssh bandit9@bandit.labs.overthewire.org -p 2220
```
Password: UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR

# Explanation
This challenge was tricky as this forced me to search how the uniq command works. I first thought that using the uniq command piped to the strings command would get the the result quickly, yet that was not the case. 

The ```uniq -u``` command works by comparing the string with those above and below it and remove the duplicate, which means if the strings are not sorted the uniq command will not work.
