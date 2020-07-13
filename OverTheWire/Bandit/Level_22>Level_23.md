# Level Goal

A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

NOTE: Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.

# Solution

1. Just as the previous Challenge, we need to view the contents of the /etc/cron.d directory.
```Bash
ls /etc/cron.d
```

2. The cron file with the name bandit23 seems to be the one for this challenge. View its contents using cat.
```Bash
cat /etc/cron.d/cronjob_bandit23
```

3. The path for the bash script should be visible now. View the contents of that bash script.
```Bash
cat /usr/bin/cronjob_bandit23.sh
```

The script seems to create a file which contains the password of the currently logged user. The file is named using the hash of a string containing the logged in user. Maybe someone logged into bandit23 before and the script was executed. So if I created a manual hash I can find the password.

4. Find the hash of that string manually.
```Bash
mytarget=$(echo I am user bandit23 | md5sum | cut -d ' ' -f 1)
```

5. View the contents of that file.
```Bash
cat /tmp/$mytarget
```
The password should be visible now.

6. Exit the bandit22 shell
```Bash
exit
```

7. ssh into bandit23
```Bash
ssh bandit22@bandit.labs.overthewire.org -p 2220
```
Password: jc1udXuA1tiHqjIsL8yaapX5XIAI6i0n
