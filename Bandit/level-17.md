# Description :
* There are 2 files in the homedirectory: passwords.old and passwords.new. The password for the next level is in passwords.
New and is the only line that has been changed between passwords.old and passwords.new
NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19



# Solution

* Run `ssh -i key.private bandit17@bandit.labs.overthewire.org -p 2220` command by using the pkey from previous stage
* Run `diff passwords.old passwords.new` command and see the following output
```
42c42
< 09wUIyMU4YhOzl1Lzxoz0voIBzZ2TUAf
---
> hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
```
* So the new password should be `hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg`