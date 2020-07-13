# Level Goal
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

NOTE: Try connecting to your own network daemon to see if it works as you think

# Solution 

1. Open a second terminal and login with the same credentials from the last level again.
```Bash
ssh bandit20@bandit.labs.overthewire.org -p 2220
```
Password: GbKksEFF4yrVs6il55v6gwY5aVje5f0j

2. Use that second window to open up a port using nc and echo the current password through that port.
```Bash
echo GbKksEFF4yrVs6il55v6gwY5aVje5f0j | nc -l -p 3300
```
Note that you can choose any port number you like as long as it was not pre-assigned to another service.

3. In the first window use the setuid file to connect to the opened port from the second window so that the password would echo there.
```Bash
./suconnect 3300
```
The password should now be visible in the second screen.

4. Exit bandit20 shell.
```Bash
exit
```

5. ssh into bandit21
```Bash
ssh bandit21@bandit.labs.overthewire.org -p 2220
```
Password: gE269g2h3mw3pwgrj0Ha9Uoqen1c9DGr

## Pro tip

Instead of using 2 terminal, ```&``` could be used to let the process run in the background.

# Explanation

In this challenge we successfully set up our own TCP server using nc.


