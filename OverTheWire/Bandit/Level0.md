# Level Goal
The goal of this level is for you to log into the game using SSH. The host to which you need to connect is bandit.labs.overthewire.org, on port 2220. The username is bandit0 and the password is bandit0. Once logged in, go to the Level 1 page to find out how to beat Level 1.

# Solution
 ```Bash
 ssh bandit0@bandit.labs.overthewire.org -p 2220
 ```
 Password: bandit0
 
 # Explaination
 SSH (Secure Shell) is used here to connect to the game host which is a linux machine. 
 SSH can be used by the domain name only which would lead to the following defaults:
 1. The port number would be set as defualt which is 22. 
 2. The username would be set as the same username of the person who wrote the command (client)
