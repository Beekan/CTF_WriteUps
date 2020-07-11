# Level Goal

The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

# Solution

1. Pass the contents of the text file to the translate command which translates the range of letters into another range.
```Bash
cat data.txt | tr "A-Za-z" "N-ZA-Mn-za-m"
```
The password should be visible now.

2. Exit bandit11 shell
```Bash
exit
```

3. ssh into bandit12
```Bash
ssh bandit12@bandit.labs.overthewire.org -p 2220
```
Password: 5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu

# Explanation

The tr command here is used for direct translation. The letters are NOT rotated using addition or subtraction.
