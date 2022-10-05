# Description :
* The password for the next level is stored in the file data.txt and is the only line of text that occurs only once

# Solution

* Run `ssh bandit8@bandit.labs.overthewire.org -p 2220` command
* Use `TESKZC0XvTetK0S9xNwm25STk5iWrBvP` as the password from previous level
* The duplicate lines are scattered. Unique command works only with adjacent duplicate lines. 
  So we are going to use first `sort` then `unique` command.  
* Run `sort data.txt |unique -u` command and see the output is `EN632PlfYiZbn3PhVK3XOGSlNInNE00t`