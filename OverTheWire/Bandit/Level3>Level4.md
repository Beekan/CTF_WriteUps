# Level Goal

The password for the next level is stored in a hidden file in the inhere directory.

# Solution

1. Navigate into the inhere directory
```Bash
cd inhere/
```

2. View the contents of the directory to know the filename
```Bash
ls .*
```
You should now see a file name called .hidden.

3. View the contents of .hidden.
```Bash
cat .hidden
```
You should be able to view the password now.

4. Exit bandit3 shell
```Bash
exit
```

5. ssh into bandit4
```Bash
ssh bandit4@bandit.labs.overthewire.org -p 2220
```
Password:pIwrPrtPN36QITSp3EQaw936yaFoFgAB

# Explanation

Hidden files cannot be viewed normally without the inclusion of '.' in the command. the 'ls .*' command translates to view all the files that start with a dot, which are the hidden files.
