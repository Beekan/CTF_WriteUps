# Level Goal
The password for the next level is stored in a file called spaces in this filename located in the home directory

# Solution
1. We already know the file name from the level goal so use cat to view the contents
```Bash
cat spaces\ in\ this\ filename
```
You should now be able to view the password.

2. Exit bandit2 shell.
```Bash
exit
```

3. ssh into bandit3.
```Bash
ssh bandit3@bandit.labs.overthewire.org -p 2220
```
Password:UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK

# Explanation

Since spaces between words in a bash command translate to signal different options each word in the filename would be viewed as a independent parameter except the woord spaces. To counter this and to signal to bash that this is just a space between the same entity the backslash character is used to signify this. 

(A general tip: you can use word completion within the command line using 'tab' and the whole filename would be properly written.)

