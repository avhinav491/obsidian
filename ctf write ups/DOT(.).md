challenge description : Can you see everything in the directory? If yes, read `flag.txt` and submit its contents.

Credentials:

```
Username: ctfplayer
Password: ctfplayer
```
level : very easy 
i created the instance for the ctf 

since it was first time doing the ctf , i wasnt aware about the ssh commands so i search the way to to join ctf challenge in linux using credentials

i learnt about ssh and its basic syntax  and figure out last part is port number which is connect by 
``
```
ssh -p "portnumber" username@hostname
```
i typed yes to record the footprint and enter the password


the terminal had different random character instead of username and hostname so i knew i am in server

i read the description of the ctf and got idea that we need to use ls command to see files in dictionary 
``` 
ls
```


i see no result when typing ls command . since it is initial ctf , i had a hunch that  challenge wont ask us to  search each dictionary . then  i remembered that ls has extra flag to see hidden files from handbook  . i typed 
```
ls -al 
```

 and boom there was a .flag.txt 
 
 i cat the file and submit the flag then destroy the instance
 ```
 cat .flag.txt
 ```
 
 