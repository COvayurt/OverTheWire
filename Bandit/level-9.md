# Description :
* The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

# Solution

* Run `ssh bandit9@bandit.labs.overthewire.org -p 2220` command
* Use `EN632PlfYiZbn3PhVK3XOGSlNInNE00t` as the password from previous level
* The data has lots of unreadable lines, can be seen with `cat data.txt` command
* Run `strings data.txt |grep ===` command and see the output:
  * `========== the
    bu========== password
    4iu========== is
    ========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s`
