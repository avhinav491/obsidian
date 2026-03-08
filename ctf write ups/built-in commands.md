
I mistakenly delete some commands, now i can't read `-flag.txt` I hope you'll find the way.

Credentials:

```
Username: ctfplayer
Password: ctfplayer
```

**Level: Very Easy**

i  connected to the server using ssh and given credentials. i tried to see if  there is anything in current directory by using ls command but  the terminal responds with command not found . i typed help to see all the commands that works since help lists all built in commands

```
help
```

now i see that read is also  a builtin commands .i knew i need to use this command. i typed read syntax like cat to read the file but it didnt works.

so i tries help flag on read

```
read --help
```

i learn that read is more like a variable reader then a filer reader so i thought i might need to input files using << into read .it didnt work and then i tried < .< is output is better then << but i was saying file dont exist so i thought it might be like the previous challenge and use -flag.txt.it show no out but did indicate the file exist  . 

```
read <-flag.txt
```

now i tried to use -u for file descriptor thinking it might work but it  didn't .i read the read files again and noted that it say read is stored in  REPLY if no names is supplied so i conclude if my previous process of inputting files is correct then reply must have the value and i can retrieve it using the echo .

```
read <-flag.txt
echo REPLY
```

i use the previous command again then echo the result of reply. it didn't work so i search about the variables in google and find out variables uses $ sign then i tried again using $sign and it worked
```
read <-flag.txt
echo $REPLY
```