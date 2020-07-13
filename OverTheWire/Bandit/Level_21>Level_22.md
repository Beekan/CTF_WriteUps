# Level Goal

A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

# Solution

1. View the contents of the cron.d directory
```Bash
ls /etc/cron.d
```
2. Now you should be able to see the desired file to operate on. View the contents of that cron file to see what bash script it runs.
```Bash
cat /etc/cron.d/cronjob_bandit22
```

3. The path for the bash script should be visible now. We can view the bash script to see what the next step should be.
```Bash
cat /usr/bin/cronjob_bandit22.sh
```

4. The bash scripts copys the password of the next file to a file in the tmp directory. Use cat to view the contents of that file.
```Bash
cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
```
You should be able to view the password now.

5. Exit bandit21 shell.
```Bash
exit
```

6. ssh into bandit22.
```Bash
ssh bandit22@bandit.labs.overthewire.org -p 2220
```
Password: Yk7owGAcWjwMVRwrTesJEwB7WVOiILLI

# Explanation

The description of the cron file is written in the Level goal, this is just retracing the steps from there.




