# Level Goal
The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)

# Solution

1. Create a directory in /tmp.
```Bash
mkdir /tmp/bandit12
```

2. Copy the data from the file to that directory for easy manipulation.
```Bash
cp data.txt /tmp/bandit12/data
```

3. Revert the hexdumb to binary and put the output in another file.
```Bash
xxd -r data > binaryData
```

4. Use file command to see what is the format of the output.
```Bash
file binaryData
```

5. The output from the file command showed that the file is compressed using gzip. So to uncompress the file, Firstly the extension needs to be changed to match that compression algorithm.
```Bash
mv binaryData binaryData.gz
```

6. Uncompress the file using gzip.
```Bash
gzip -d binaryData.gz
```

7. Use file command to see what is the format of the file.
 ```Bash
 file binaryData
 ```
 
 8. The output of the file command showed that the file is compressed using bzip2. change the extension of the file to match that compression.
 ```Bash
 mv binaryData binaryData.bz2
 ```
 
 Repeat the process above from step 4 to step 8 with choosing what the extension and compression algorithm is according to the output of the file command.
 
 9. A third compression algorithm is going to be used along the way which is tar. The same method is going to be used as above, nothing is changed except the name of the command and the extension.
 ```Bash
 mv binaryData binaryData.tar
 ```
 
 10. Extract the files from the tar file.
 ```Bash
 tar -xf binaryData.tar
 ```
 Then continue to repeat as above again.
 
 The steps are going to repeat for 9 times.
 
 11. Exit bandit12 shell
 ```Bash
exit
```

12. ssh into bandit13
```Bash
ssh bandit13@bandit.labs.overthewire.org -p 2220
```
Password: 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL

# Explanation

This challenge is aimed at understanding what the function of extensions are and how to use file command efficiently. The compression algorithms are used interchangebly to be able to test different outputs from the file command.

