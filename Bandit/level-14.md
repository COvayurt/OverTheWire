# Description :
* The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.

# Solution

* Run `ssh -i ssh.private bandit14@bandit.labs.overthewire.org -p 2220` command
* Use `sh.private` file from previous level
* Also, logged in and run `cat /etc/bandit_pass/bandit14` to see the password, which is `fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq`
* Then submitted this stage's password to localhost:30000 by executing the `nc localhost 30000` command. It gives us the next level's password
  * ```
    fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
    Correct!
    jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
    ```