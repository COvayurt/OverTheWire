# Description :
* The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) 
  letters have been rotated by 13 positions

# Solution

* Run `ssh bandit11@bandit.labs.overthewire.org -p 2220` command
* Use `6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM` as the password from previous level
* The file has `Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi` in it. Has been rotated with `Rot13`
* So to be able to reverse this, we should map `{N..Z} {A..M} {n..z} {a..m}` to `{A..Z} {a..z}`
* Run `cat data.txt | tr "$(echo -n {N..Z} {A..M} {n..z} {a..m} | tr -d ' ')" "$(echo -n {A..Z} {a..z} | tr -d ' ')"` command
  * The output will be `The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv`
