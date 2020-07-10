# Level Goal

The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:

1. human-readable

2. 1033 bytes in size

3. not executable
 
# Solution

The Solution is quite easy and could be reached in one step after studying the options of the file command.

The solution command is as follows:

```Bash
find -size 1033c ! -executable -exec sh -c 'file -b $0 | grep -q ASCII' {} \; -exec cat {} \;
```
The password should be visible by now.
"See Explaination section for a more simple solution"

2. Exit bandit5 shell
```Bash
exit
```

3. ssh into bandit6
```Bash
ssh bandit6@bandit.labs.overthewire.org -p 2220
```

Password: DXjZPULLxYr17uwoI01bNLQbtFemEgo7

# Explaination

This challenge is quite interesting as it teaches on both the technical and methodological side or the trainee.


## First is the technical side:

The find command could be partitioned into four segments for easier explaination.
1. The size option allows the user to find files with a certain size in bytes. Note that the size is followed by 'c' this is to indicate that this is the actaul byte size. 'b' is another option that represents the size in 512 byte blocks.

2. ```! -executable``` is to indicate that the file is NOT an executable. Fairly straight forward.

3. ```-exec sh -c 'file -b $0 | grep -q ASCII' {} \;``` This option is used to find files that are humanly readable. To explain this, it has to be broken down into 3 Parts.  
  - First being the ```-exec sh -c``` option which indicates that whatever comes following this is a fully fledged bash script that end at the delimeter ```\;``` and exists only between the quotations. 
  - Second Part is the file command which returns the properties of the file that is reported from the find command. The file command is executed quietly using the ```-b``` option, note that this does not change the correctness of the command it just makes reading the output from the cat command easier. 
  Note that the argument of the file command is ```$0```. This character indicates that it is constantly being replaced by the input given to it from the find command wich is given through the curly brackets ```{}```.
  - Third part is ```| grep -q ASCII``` which filters the output of the file command to find only the files which conatins ASCII.
  - The script is then delimeted by the ```\;``` charchter which indicates the end of the bash script.
 4. ```-exec cat {} \;``` This command takes the final output which has been filtered through the file command that preceded it and other options applied and prints out the contents of the desired file. The path of the file is passed to the cat command through the curly bracket ```{}``` 
 

 
 
## Second is the methodolgical Approach:
 
 Seeing the context of the desired features of the file one feature stand out quite obviously which is the 1033 byte size file. This option is very specific and not a lot of other files could have the same size. Thus noticing that the find command could be used as follows 
 ```Bash
 find -size 1033c -exec cat{} \;
 ```
 which is a much smaller and less complicated command and has better performance. 
 
 The lesson learned here is do not make the Challenge more complex than it needs to be. Understand the context of the challenge and the deliverables needed. Figure out which are essential and start from there.
