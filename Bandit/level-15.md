# Description :
* The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL encryption. 
  Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. 
  Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…

# Solution

* Run `ssh bandit15@bandit.labs.overthewire.org -p 2220` command
* Use `jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt` as the password from previous level
* Well, run `openssl s_client -connect localhost:30001` to be able to establish a secure connection to the server.
* At the end, submit the current level's password `jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt`. Viola!
* Server returns 
  * ```
    Correct!
    JQttfApK4SeyHwDlI9SXGR50qclOAil1
    closed
    ```
