# Description :
* The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:
  * human-readable
  * 1033 bytes in size
  * not executable

# Solution

* Run `ssh bandit5@bandit.labs.overthewire.org -p 2220` command
* Use `lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR` as the password from previous level
* Run `ls` command and see `inhere` directory.
* Get in to the directory `cd inhere`
* Run `ls` and see the output :
  * `maybehere00  maybehere02  maybehere04  maybehere06  maybehere08  maybehere10  maybehere12  maybehere14  maybehere16  maybehere18
    maybehere01  maybehere03  maybehere05  maybehere07  maybehere09  maybehere11  maybehere13  maybehere15  maybehere17  maybehere19`
* Run `find . -type f -size 1033c |xargs file` command. See the output:
  * `./maybehere07/.file2: ASCII text, with very long lines (1000)`
* Run `cat ./maybehere07/.file2`. See output is : `P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU`