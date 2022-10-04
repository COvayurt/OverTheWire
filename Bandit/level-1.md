* Run `ssh bandit1@bandit.labs.overthewire.org -p 2220` command
* Use `NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL` as the password from previous level
* Run `ls` in `/home/bandit1`
  * See output `4 -rw-r-----  1 bandit2 bandit1   33 Sep  1 06:30 -`
  * Most probably the password is in `-` file
* Run `cat ./-` command. See details from `https://stackoverflow.com/a/42187582/1772302`
* See output is `rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi`
