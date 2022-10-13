# Description :
* The password for the next level is stored in a file readme in the homedirectory. 
Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.



# Solution

* Run `ssh bandit18@bandit.labs.overthewire.org -p 2220` command
* Use `hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg` as the password from previous level
* This time it kicks me out whenever I try to log in and write 
```
....
Byebye !
Connection to bandit.labs.overthewire.org closed.
```
* It seems like I can not log in but I am able to send my command via SSH
* Run `ssh bandit18@bandit.labs.overthewire.org -p 2220 -C 'ls'` to see the files in the home dir. Output is `readme`
* Then run `ssh bandit18@bandit.labs.overthewire.org -p 2220 -C 'cat readme'` and viola! The output is `awhqfNnAbc1naukrpqDYcF95h7HoMTrC`
