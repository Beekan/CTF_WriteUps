# Level Goal
The password for the next level is stored somewhere on the server and has all of the following properties:

1. owned by user bandit7

2. owned by group bandit6

3. 33 bytes in size

# Solution

This challenge like the previous one is oriented around the find command. The solution is fairly easy as well and integrated within the find command.
1. Run the following command:
```Bash
find /  -group bandit6 -user bandit7 -size 33c 2>/dev/null -exec cat {} \;
```
The password should be visible by now.  
2. Exit bandit6 shell
```Bash
exit
```

3. ssh into bandit7
```Bash
ssh bandit7@bandit.labs.overthewire.org -p 2220
```

Password: HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs

# Explanation

I first thought of using ``` find -size 33c``` as the previous challenge, but surprisingly nothing show up. I then used ls to see whether there are actually any files within the active directory or not and I found out that there was none. The keyword was "somewhere in the server" written in the level goal. So I used find in the root directory by using ```find \ -size 33c```. Here I found some progress that files resulted from that but still alot of files and the needed one was not apparent. So I used other options to aid in the search such as ```-user``` and ```-group``` which were specified in the level goal. I then found that all the files returned an error of permission denied expect for a single one so I directed all the errors towards the null file. This is done through ```2>\dev\null```. The number 2 is used to denote stderr which in this case referes to the outputs with permission denied. The cat command execution is used as before.
