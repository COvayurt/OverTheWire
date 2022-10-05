# Description :
* The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. 
  For this level it may be useful to create a directory under /tmp in which you can work using mkdir. 
  For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)

# Solution

* Run `ssh bandit12@bandit.labs.overthewire.org -p 2220` command
* Use `JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv` as the password from previous level
* The `data.txt` file is a hex dump of a file. So we are going to create a file from this dump.
* Move the file under `/tmp/`. Creating a dir using `mkdir /tmp/ma_baby`
* Moving the file `cp data.txt /tmp/ma_baby`. 
* Change current dir `cd /tmp/ma_baby`
* Run `xxd -r data.txt > data`
* Run `file data` to get the file information. Output : `data: gzip compressed data, was "data2.bin", last modified: Thu Sep  1 06:30:09 2022, max compression, from Unix, original size modulo 2^32 575`
* Run `mv data data.gz && gzip -d data.gz && ls`. Output: `data data.txt`
* Run `file data`. Output:`data: bzip2 compressed data, block size = 900k`. So the data has compressed with `bzip2`
* Run `mv data data.b2z && bzip2 -dk data.b2z && ls` and output will be `data.b2z  data.b2z.out  data.txt`
* Run `file data.b2z.out`. Output: `data.b2z.out: gzip compressed data, was "data4.bin", last modified: Thu Sep  1 06:30:09 2022, max compression, from Unix, original size modulo 2^32 20480`
* Run `mv data.b2z.out data.gz && gzip -d data.gz && ls`. Output : `data  data.b2z  data.txt`
* Run `file data`. Output will be `data: POSIX tar archive (GNU)`
* Run `mv data data.tar && tar -xvf data.tar` command. Output will be `data5.bin`
* Run `file data5.bin` command. Output will be `data5.bin: POSIX tar archive (GNU)`
* Run `mv data5.bin data5.tar && tar -xvf data5.tar`. Output will be `data6.bin`
* Run `file data6.bin` command. Output will be `data6.bin: bzip2 compressed data, block size = 900k`
* Run `mv data6.bin data_6.b2z && bzip2 -dk data_6.b2z` command. Output will be `bzip2: Can't guess original name for data_6.b2z -- using data_6.b2z.out`
* Run `file data_6.b2z.out` command. Output will be `data_6.b2z.out: POSIX tar archive (GNU)`
* Run `mv data_6.b2z.out data_6.tar && tar -xvf data_6.tar` command. Output will be `data8.bin`
* Run `file data8.bin` command. Output will be `data8.bin: gzip compressed data, was "data9.bin", last modified: Thu Sep  1 06:30:09 2022, max compression, from Unix, original size modulo 2^32 49`
* Run `mv data8.bin data8.gz && gzip -d data8.gz && ls` command. Output will be : `data5.tar  data_6.b2z  data_6.tar  data8  data.b2z  data.tar  data.txt`
* Run `file data8` command. Output will be `data8: ASCII text`
* Viola! now we can just cat the file. Run `cat data8` command. Output will be `The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw`