# Description: 
* The password for the next level is stored in the only human-readable file in the inhere directory. 
* Tip: if your terminal is messed up, try the “reset” command.

# Solution

* Run `ssh bandit4@bandit.labs.overthewire.org -p 2220` command
* Use `2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe` as the password from previous level
* Run `ls` command and see `inhere` directory.
* Get in to the directory `cd inhere`
* Run `ls` and see the output
  * `-file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09`
* Run command `find . |xargs file`
  * `.:         directory
    ./-file03: data
    ./-file04: data
    ./-file09: data
    ./-file07: ASCII text
    ./-file08: data
    ./-file06: data
    ./-file05: data
    ./-file01: data
    ./-file02: data
    ./-file00: OpenPGP Public Key`
* Run command `cat ./-file07` and see the output is `lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR`