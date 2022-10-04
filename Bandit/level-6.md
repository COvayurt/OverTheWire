# Description :
* The password for the next level is stored somewhere on the server and has all of the following properties:
  * owned by user bandit7
  * owned by group bandit6
  * 33 bytes in size

# Solution

* Run `ssh bandit6@bandit.labs.overthewire.org -p 2220` command
* Use `P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU` as the password from previous level
* Run `ls` command and saw no output.
* Run `find / -user bandit7 -group bandit6 -size 33c 2>/dev/null` command. See the output is `/var/lib/dpkg/info/bandit7.password`
* Run `cat /var/lib/dpkg/info/bandit7.password` and see output is `z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S`