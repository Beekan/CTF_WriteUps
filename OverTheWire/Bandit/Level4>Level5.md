# Level Goal

The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.

# Solution 

1. cd (change directory) into the inhere directory.
```Bash
cd inhere/
```

2. Use 'ls' to view the filenames within the directory.
We find that the filenames all start with a dash.

3. Find the human-readable file using the file command. 
```Bash
file ./*
```
0r
```Bash
file -- *
```
We find that -file07 is the only humanly readable one. (The only file that contains ASCII text)

4. View the contents of the file.
```Bash
cat ./-file07
```
or
```Bash
cat -- -file07
```
5. exit bandit4 shell
```Bash
exit
```

6. ssh into bandit5
```Bash
ssh bandit3@bandit.labs.overthewire.org -p 2220
```
Password:koReBOKuIDDepwhWk7jZC0RTdopnAYKh

# Explanation
The filenames start with a dash which would make the dash itself and the first letter to be interpreted as an option for the command. 

To combat this we can use one of 2 solutions: 
1. Use the option delimeter '--' which when used means that whatever comes after is treated as an operand.
2. Hide the dash by using './' before the filename.
