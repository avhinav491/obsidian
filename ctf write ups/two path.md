There is always two way to solve a problem!!!

Credentials:

```
Username: ctfplayer
Password: ctfplayer
```

**Level: Very Easy**

i  connected to the server using ssh and given credentials. i knew that we need to find some files which must have flags so i checked the files in directory. 
```
ls
```

i found the files named -flag.txt so i try to cat the files but it was not working . i realized the problem is with the hyphen so i decide to  use full path so hyphen gets covered inside it and wont de considered a flag by terminal. it works

```
cat ../ctfplayer/-flag.txt
```

