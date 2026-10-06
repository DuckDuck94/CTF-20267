# [Week 2] sw-elevator
There were 14 levels to this challenge (I asked so I knew my progress in an attempt to finish it really fast).  Technically 15 levels as they were labelled from index 0 xp.  Mayhaps i might just list all the levels here

Much of this was solved with background knowledge, and if I didnt remember the syntax, it took a few minutes of looking it up.  Some things stumped me but after a little research I quickly understood what the hints were telling me.   
Forewarning, these explainations aren't very technical and are also probably wrong O-O but the gist is there and is what my thought process was while using these commands.

After final reflection, I think that this challenge helped me brush up my skills on using the Linux terminal to navigate files and executables :). 

overall very fun challenge !!

### [Level 0]
The ```ls``` command: Lists all files
<br>```cat```: Reads file
<br>```cd```: Enter directory

Using these simple commands, I was able to read the hint, located in the README and get the credentials for the next level, located in the creds_level1.txt

### [Level 1]
```grep -r <string>```: search for string recursively through all directories

Knowing the structure used for getting the username for the next level, I used the grep command with the recursive, -r, flag to look within all of the files for the string "level2."  That would give me the location/path of where the next creditials are located.

### [Level 2]
```grep <string> <file>```: search for string within a file

Similar to the previous level, this command looked for the credentials with a specific string

### [Level 3]
```chmod ug+rwx <executable>```: give executable access

Since this levels hint was something abotu credentials, I thought I should give myself more privilages to the executable file.  After running it (with ./<file>), it gave me the next level's credentials.

### [Level 4]
```ls -a```: reveal all files (including hidden)

The way i knew this had to be a chellenge >:3 a simple flag can reveal hidden files, marked with a period (.) before the file name

### [Level 5]
```special and hidden characters```: lowkey just used the tab to autopopulate the name O-O

But seriously (and in addition), spaces are considered special characters and need the backslash to properly register to the command line

### [Level 6]
```env```: Environment variable is a hidden folder that can contain information that runs in the background and sometimes sensitive credentials

Opening this file revealed a secret key.  Also in this level was an executable that seemed to be missing that password.  After running ./<executable> <super secret password>, I was able to run the password protected executable :)

### [Level 7]
```cd /```: enter root directory

I honestly thought that root in the hint meant like root user, but no. just the directory lol.  Most times, ```cd``` is in the home directory, represented by "~" while root can be acced with a "\."  It isnt very usual to store things in the root directory other than background items
Oh! here was where we found the flags! we could open teh first one, but it seemed like teh second one was locked (remember this for later)

### [Level 8]
```ps -ef | grep <string>```: list all running processes and look for a specific string

In this scenario, there is a server already running, so all you needed to do is find the running processes.  I initially used the string "level9" but it wasn't specific enough.  In the intructions (I didnt notice this), it mentioned that the numbers at the end of the levels were all the same.  After grepping for "level9_number," it was more specific and I was able to find the specific line.

### [Level 9]
```:q```

Classic vim moment. (the classic "how to escape vim" hahaha)

### [Level 10]
```strings```: print the sequences of printable characters in files (source: linux man page)

The hint said "STRINGS" in big bold capital letters...HMMM i wonder what that command must mean... -_- lowkey dont even know what the file originaly was. maybe it was a directory lol *speedrun noises*

### [Level 11]
```vim > R```

Since it seemed like the file crashed, I thought I could go back and look at the vim history or something.  Upon opening it, It siad that "oh no. the file crashed before saving. here are the options to restore (R) it."  As simple as vim is, i did "R > Enter".  Simple as that!

### [Level 12]
```curl localhost:<port>```: Open a self-hosted page from the command line

Giveaway hints were "localhost," "port," and "reach from the command line." HMMMMMM...curl is usually used to read pages form teh commandline...mayhaps...if there were a syntax (i did have to look this one up)...to open said page..

### [Level 13]
```tar -xvzf <compressed file>.tar.gz```: unzip mega conpressed file

O-O the way ive had to use this to open files in Kali (remember this if you think Kali Linux has EVERYTHING..they do..but compresed).  Very silly challenge, similar silliness to the "oh no how to exit vim" meme 

### [Level 14]
DONE !! 

...Suspicious tellign us to go back to /flag2.txt...
oh! :D now we can access it... -_- and now it says "no longer a linux larper" 

LARPER!?! (づ ò ___ ó )づ ┻━┻
