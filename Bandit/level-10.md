# Description :
* The password for the next level is stored in the file data.txt, which contains base64 encoded data

# Solution

* Run `ssh bandit10@bandit.labs.overthewire.org -p 2220` command
* Use `G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s` as the password from previous level
* Run `cat data.txt` command. Output is `VGhlIHBhc3N3b3JkIGlzIDZ6UGV6aUxkUjJSS05kTllGTmI2blZDS3pwaGxYSEJNCg==`. This is obviously a Base64 string.
* Run `cat data.txt |base64 --decode` to see it decoded: `The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM`