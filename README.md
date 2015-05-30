#Wargames#

A wargame (or war game) in hacking is a security challenge in which one must exploit or defend a vulnerability in a system or application or gain or prevent access to a computer system.

A wargame usually involves semantic URL attacks, knowledge-based authentication, password cracking, reverse engineering of software (mostly JavaScript, Adobe Flash, and assembly language), code injection, SQL injections, cross-site scripting, exploits, IP address spoofing, and other hacking techniques.

##Bandit##

###Level 0###
The goal of this level is for you to log into the game using SSH. The host to which you need to connect is **bandit.labs.overthewire.org**.  Using PuTTY session connect to the host.

![Capture1](https://cloud.githubusercontent.com/assets/12239510/7896777/0cb0944c-06e3-11e5-9e67-dbe4db5dd769.JPG)

	username: bandit0
	password: bandit0 

Once logged in, go to the Level 1 page to find out how to beat Level 1.

![Capture2](https://cloud.githubusercontent.com/assets/12239510/7896779/22f9a1c6-06e3-11e5-81f0-3824c90a7b67.JPG)


###Level 0 -> Level 1###
The password for the next level is stored in a file called **readme** located in the home directory. Use this password to log into ***bandit1*** using SSH. Whenever you find a password for a level, use SSH to log into that level and continue the game. This level requires **ls** and **cat** commands to find *readme* file and to read the password.

![Capture3](https://cloud.githubusercontent.com/assets/12239510/7896778/22f09202-06e3-11e5-886d-ede83f03f81f.JPG)

	username: bandit1
	password: boJ9jbbUNNfktd78OOpsqOltutMc3MY1

![Capture4](https://cloud.githubusercontent.com/assets/12239510/7896780/23045e68-06e3-11e5-9e24-9430eb367caa.JPG)


###Level 1 -> Level 2###
The password for the next level is stored in a file called **-** located in the home directory. 

We need to delimit the dash to read it, since it is a special character. With bash redirection, **-** is not recognised as a special filename, so bash will use that as the literal filename.  We have to specify that the file name is actually dash in the directory we are in. The usual way of doing this is to prefix the filename with a path **./-**

![Capture5](https://cloud.githubusercontent.com/assets/12239510/7896783/231fb50a-06e3-11e5-9624-9d92e825aad7.JPG)

	username: bandit2
	password: CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9

![Capture6](https://cloud.githubusercontent.com/assets/12239510/7896781/230e8f64-06e3-11e5-87fe-a19d768204f3.JPG)


###Level 2 -> Level 3###
The password for the next level is stored in a file called **spaces in this filename** located in the home directory. Since the filename contains spaces, filename can be enclosed within double quotes or escape spaces with **\\**

![capture7](https://cloud.githubusercontent.com/assets/12239510/7896782/23166f72-06e3-11e5-8e65-7abb7d3b488b.JPG)

	username: bandit3
	password: UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK

![capture8](https://cloud.githubusercontent.com/assets/12239510/7896784/2334aa6e-06e3-11e5-9863-4e05c9ac0423.JPG)


###Level 3 -> Level 4###
The password for the next level is stored in a hidden file in the ***inhere*** directory. Inside the *inhere* directory there is a hidden file called **hidden**.

![capture9](https://cloud.githubusercontent.com/assets/12239510/7896785/233c5d40-06e3-11e5-9b4f-c1c0c08871d7.JPG)

	username: bandit4
	password: pIwrPrtPN36QITSp3EQaw936yaFoFgAB

![capture10](https://cloud.githubusercontent.com/assets/12239510/7896786/23488b38-06e3-11e5-91fc-6f4af6d807e1.JPG)


###Level 4 -> Level 5###
The password for the next level is stored in the only human-readable file in the ***inhere*** directory. The only human-readable file is **-file07**. The **file** linux command type printed will usually contain one of the words text (the file contains only printing characters and a few common control characters and is probably safe to read on an ASCII terminal), executable (the file contains the result of compiling a program in a form understandable to some UNIX kernel or another), or data meaning anything else (data is usually `binary' or non-printable). 

![capture11](https://cloud.githubusercontent.com/assets/12239510/7896787/2354f5b2-06e3-11e5-9e56-3a2ba0129864.JPG)

	username: bandit5
	password: koReBOKuIDDepwhWk7jZC0RTdopnAYKh

![capture12](https://cloud.githubusercontent.com/assets/12239510/7896788/235dae46-06e3-11e5-8302-f0f24a23ed77.JPG)


###Level 5 -> Level 6###
The password for the next level is stored in a file somewhere under the ***inhere*** directory and has all of the following properties: - human-readable - 1033 bytes in size - not executable.

![capture13](https://cloud.githubusercontent.com/assets/12239510/7896789/23682b82-06e3-11e5-8ac0-84050bcb100e.JPG)

**find** command would search for files in a directory hierarchy, so this feature can be used to find human-readable and non executable file using **-type** option. And also, **-size** option can be used to identify a file with 1033 bytes. Since the file needs to be a regular file, it requires to use **-type f**.

**-size n[bckw]** - File uses n units of space. The units are 512-byte blocks by default or if b' follows n, `bytes if c' follows n`, kilobytes if k' follows n, or 2-byte words if w' follows n. The size does not count indirect blocks, but it does count blocks in sparse files that are not actually allocated.

![capture14](https://cloud.githubusercontent.com/assets/12239510/7896790/23799016-06e3-11e5-8527-36aae0676efa.JPG)

	username: bandit6
	password: DXjZPULLxYr17uwoI01bNLQbtFemEgo7

![capture15](https://cloud.githubusercontent.com/assets/12239510/7896791/23833b02-06e3-11e5-8581-ab8450168fd1.JPG)


###Level 6 -> Level 7###
The password for the next level is stored somewhere on the server and has all of the following properties: - owned by user bandit7 - owned by group bandit6 - 33 bytes in size. There are no files inside the home directory. So it requires to find every file under the directory **/ (or root)** owned by the user bandit7 and the group bandit6 with the file size 33 in bytes.

**2>/dev/null** - **2>** redirects stderr to file, and **/dev/null** is the null device it takes any input you want and throws it away. It can be used to suppress any output.

![capture16](https://cloud.githubusercontent.com/assets/12239510/7896792/238db672-06e3-11e5-92ec-c3d0d63c57ab.JPG)

	username: bandit7
	password: HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs

![capture17](https://cloud.githubusercontent.com/assets/12239510/7896793/23999c6c-06e3-11e5-803a-0dcd06b77f52.JPG)


###Level 7 -> Level 8###
The password for the next level is stored in the file **data.txt** next to the word ***millionth***. The ***data.txt*** file contains huge information, so we could use **grep** command to find the lines where contains ***millionth***.

![capture18](https://cloud.githubusercontent.com/assets/12239510/7896794/23a64e8a-06e3-11e5-9518-29b4ba19fbc3.JPG)

	username: bandit8
	password: cvX2JJa4CFALtqS87jk27qwqGhBM9plV

![capture19](https://cloud.githubusercontent.com/assets/12239510/7896795/23b0f178-06e3-11e5-8916-b374f4280f94.JPG)


###Level 8 -> Level 9###
The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once. To find the unique line of text within the ***data.txt*** file **uniq** command will be used with **-u** option to print only unique lines. To use ***uniq*** command the file has to be sort.

- **sort** - sort lines of text files
- **uniq** - remove duplicate lines from a sorted file, using **-u** --unique -- only print unique lines

![capture20](https://cloud.githubusercontent.com/assets/12239510/7896796/23bc8f2e-06e3-11e5-9eef-a7555e918758.JPG)

	username: bandit9
	password: UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR

![capture21](https://cloud.githubusercontent.com/assets/12239510/7896797/23c60630-06e3-11e5-9041-36864419980c.JPG)


###Level 9 -> Level 10###
The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, beginning with several ‘=’ characters. The ***data.txt*** file is a binary file, so **grep** command can not be used easily. So it requires to find what are the printable characters.

For each file given, GNU **strings** prints the printable character sequences that are at least 4 characters long (or the number given with the options below) and are followed by an unprintable character. By default, it only prints the strings from the initialized and loaded sections of object files; for other types of files, it prints the strings from the whole file. ***strings*** is mainly useful for determining the contents of non-text files.

![capture22](https://cloud.githubusercontent.com/assets/12239510/7896798/23d06148-06e3-11e5-9193-2de16c691c37.JPG)

	username: bandit10
	password: truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk

![capture23](https://cloud.githubusercontent.com/assets/12239510/7896799/23d9a0dc-06e3-11e5-9206-71ee12863076.JPG)


###Level 10 -> Level 11###
The password for the next level is stored in the file **data.txt**, which contains *base64 encoded data*.

**base64** - base64 encode/decode data and print to standard output use with **-d** option to decode data

![capture24](https://cloud.githubusercontent.com/assets/12239510/7896800/240e9364-06e3-11e5-997c-8346c05161fe.JPG)

	username: bandit11
	password: IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR

![capture25](https://cloud.githubusercontent.com/assets/12239510/7896801/241830d6-06e3-11e5-92f2-8c948ef5f04a.JPG)


###Level 11 -> Level 12###
The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions.

> **ROT-13** is a simple letter substitution cipher that replaces a letter with the letter 13 letters after it in the alphabet. 

The **tr** command automatically translates (substitutes) sets of characters.

![capture26](https://cloud.githubusercontent.com/assets/12239510/7896802/2423cb1c-06e3-11e5-9ad9-474aef338688.JPG)

	username: bandit12
	password: 5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu

![capture27](https://cloud.githubusercontent.com/assets/12239510/7896803/242dce50-06e3-11e5-8884-9ab849f3fbc3.JPG)


###Level 12 -> Level 13###
The password for the next level is stored in the file **data.txt**, which is a *hexdump* of a file that has been *repeatedly compressed*. For this level it may be useful to create a directory under /tmp in which you can work using **mkdir**. For example: mkdir /tmp/myname123. Then copy the datafile using **cp**, and rename it using **mv**.

> **hexdump** is a hexadecimal view (on screen or paper) of computer data, from RAM or from a file or storage device. Looking at a hex dump of data is commonly done as a part of debugging, or of reverse engineering. In a hexdump, each byte (8-bits) is represented as a two-digit hexadecimal number. Hexdumps are commonly organized into rows of 8 or 16 bytes, sometimes separated by whitespaces. Some hexdumps have the hexadecimal memory address at the beginning and/or a checksum byte at the end of each line.

![capture28](https://cloud.githubusercontent.com/assets/12239510/7896804/243904dc-06e3-11e5-9f18-08ee61967a21.JPG)

**xxd** creates a hexdump of a given file or standard input. It can also convert a hexdump back to its original binary form. Use the **-r** option to *convert hexdump into binary*. 

	xxd -r data1.txt data2

The ***data2*** binary file is gzip compressed file, so using **zcat** linux command and **-d** option the file can be decompress. Once we decompressed the gzip file (data2), it turns into a bzip2 archive.   

![capture29](https://cloud.githubusercontent.com/assets/12239510/7896805/244400ee-06e3-11e5-9fe8-3f2fbd392af4.JPG)

Using **bzip2** command decompress the **data3**. After decompressing the next level reveals another gzip archieve, using the **zcat** command decompressed the archive. By decompressing **data3** gzip file it gives another tar archieve.

![capture30](https://cloud.githubusercontent.com/assets/12239510/7896806/256b1958-06e3-11e5-90bf-e3dff1a9cd3a.JPG)

By using **tar** linux command with **-xvf** options, extract the file. The next level also reveals a tar archive named **data5.bin** and once extract that file it gives another bzip2 compressed file named **data6.bin**.

    -x, --extract, --get --> extract files from an archive
    -f, --file  --> use archive file or device F (default "-", meaning stdin/stdout)
    -v, --verbose --> verbosely list files processed

![capture31](https://cloud.githubusercontent.com/assets/12239510/7896809/259d72ae-06e3-11e5-9167-c9536bac4756.JPG)

After decompressing the bzip2 file ***data6.bin***, it gives a tar archive file called **data6.bin.out**. Extracting this file reveals another gzip file called **data8.bin**, and by decompressing this file gives a ASCII text file named **data9.bin** which contains the password for the next level.

![capture32](https://cloud.githubusercontent.com/assets/12239510/7896808/258943f6-06e3-11e5-8754-1c03ca1cbb3e.JPG)

	username: bandit13
	password: 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL

![capture33](https://cloud.githubusercontent.com/assets/12239510/7896810/25a521de-06e3-11e5-9959-fbc165c8462f.JPG)


###Level 13 -> Level 14###
The password for the next level is stored in **/etc/bandit_pass/bandit14** and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Note: *localhost* is a hostname that refers to the machine you are working on.

> **ssh** (SSH client) is a program for logging into a remote machine and for executing commands on a remote machine. 

![capture34](https://cloud.githubusercontent.com/assets/12239510/7896812/25b566d4-06e3-11e5-8f39-a67d84c77c96.JPG)

![capture35](https://cloud.githubusercontent.com/assets/12239510/7896807/25858860-06e3-11e5-906b-62743b15dc89.JPG)

	username: bandit14
	password: 4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e

![capture36](https://cloud.githubusercontent.com/assets/12239510/7896811/25afabea-06e3-11e5-8cba-560afb741731.JPG)

In this level the user already inside the **bandit14** user logging, so to retrieve the password of the next level (bandit15) establish a connection using **telnet** or **nc** to port 30000.


###Level 14 -> Level 15###
The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost. We can user either **telnet** or **nc (netcat)** to build the connection.

Using **telnet**;

![capture37](https://cloud.githubusercontent.com/assets/12239510/7896813/25c3b022-06e3-11e5-800b-68ffa9579c5a.JPG)

Using **nc** (netcat) utility;
	
	-n --> Do not do any DNS/service lookups on any specified addresses, hostnames/ports.

![capture38](https://cloud.githubusercontent.com/assets/12239510/7896815/2693d7ca-06e3-11e5-8038-e7156a31b4ea.JPG)
	
	username: bandit15
	password: BfMYroe26WYalil77FoDi9qh59eK5xNr


###Level 15 -> Level 16###
The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL encryption.

**Note**: Getting “HEARTBEATING” and “Read R BLOCK”? Use -quiet and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…

> **OpenSSL** is a cryptography toolkit implementing the Secure Sockets Layer (SSL v2/v3) and Transport Layer Security (TLS v1) network protocols and related cryptography standards required by them. The openssl program is a command line tool for using the various cryptography functions of OpenSSL's crypto library from the shell.

**s_client** - This implements a ***generic SSL/TLS client*** which can establish a transparent connection to a remote server speaking SSL/TLS. It's intended for testing purposes only and provides only rudimentary interface functionality but internally uses mostly all functionality of the OpenSSL ssl library

	-connect host:port --> This specifies the host and optional port to connect to. If not specified then an attempt is made to connect to the local host on port 4433.

	-quiet --> inhibit printing of session and certificate information. This implicitly turns on -ign_eof as well.

![capture39](https://cloud.githubusercontent.com/assets/12239510/7896814/25dc0d52-06e3-11e5-9670-b319c4451cba.JPG)

	username: bandit16
	password: cluFn7wTiGryunymYOu4RcffSxQluehd

This is what happen if we aren't pass the **-quiet** with the **openssl**.

![capture40](https://cloud.githubusercontent.com/assets/12239510/7896818/26c2c6ca-06e3-11e5-9838-9f7de7c74ec7.JPG)

![capture41](https://cloud.githubusercontent.com/assets/12239510/7896816/26982960-06e3-11e5-93be-ba93f19c5d8e.JPG)


###Level 16 -> Level 17###
The password for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next password, the others will simply send back to you whatever you send to it.

> **nmap** - Network exploration tool and security scanner

	-p --port ranges --> This  option specifies what ports you want to specify. For example "-p 23" will only try port 23 of the  target  host(s).

	-sV --> Version detection: After TCP and/or  UDP  ports  are  discovered using   one   of  the  other  scan  methods,  version  detection communicates with those ports to try and  determine  more  about what  is actually running.

![capture42](https://cloud.githubusercontent.com/assets/12239510/7896820/26d6028a-06e3-11e5-8c5b-dd5c7b4f0e06.JPG)

The open ports; 31000, 31046, 31691, and 31960 were not tested, since those are echo or SSH. So port number 31518 was checked but no result found.


![capture43](https://cloud.githubusercontent.com/assets/12239510/7896817/26be8a2e-06e3-11e5-9f21-02da9d845d83.JPG)

Then port 31790 was checked and another RSA private key will be given.

![capture44](https://cloud.githubusercontent.com/assets/12239510/7896822/273399d6-06e3-11e5-967c-e8c5151ea37d.JPG)

Then rename the existing sshkey.private with a new name and copy the original RSA private key to **sshkey.private**.

![capture45](https://cloud.githubusercontent.com/assets/12239510/7896819/26d13c50-06e3-11e5-907f-a42bcde66d79.JPG)

Change the access permissions of the sshkey.private and using ssh log into the next level.

	-i identity_file --> Selects a file from which the identity (private key) for RSA or DSA authentication is read.

![capture46](https://cloud.githubusercontent.com/assets/12239510/7896821/26e279d4-06e3-11e5-99b6-86d9074366b8.JPG)

Retrieve the bandit17 password, or start working on the next level.

	username: bandit17
	password: xLYVMN9WE5zQ5vHacb0sZEVqbrp7nBTn

![capture47](https://cloud.githubusercontent.com/assets/12239510/7896823/28008a0e-06e3-11e5-8dcd-c83db87ff35e.JPG)


###Level 17 -> Level 18###
There are 2 files in the home directory: **passwords.old** and **passwords.new**. The password for the next level is in *passwords.new* and is the only line that has been changed between passwords.old and passwords.new

NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into **bandit18**, this is related to the next level, **bandit19**.

**diff** compares the contents of the two files from-file and to-file. The new password is the only line different between two files.

**42c42** means **4,2 c 4,2**

**4,2** - line numbers corresponding to the first file,
**c** - a letter (a for add, c for change or d for delete)
**4,2** - line numbers corresponding to the second file.

In our output above, "**42c42**" means: "*Lines 4 through 2 in the first file need to be changed in order to match lines 4 through 2 in the second file*." 

It then tells us what those lines are in each file: Lines preceded by **<** are lines from the first file. Lines preceded by **>** are lines from the second file.

	username: bandit18
	password: kfBf3eYk5BPBRzwjqutbbfE887SVc5Yd

![capture48](https://cloud.githubusercontent.com/assets/12239510/7899220/a5e75ac8-0739-11e5-9e58-1a2735c36c48.JPG)


###Level 18 -> Level 19###
The password for the next level is stored in a file **readme** in the home directory. Unfortunately, someone has modified **.bashrc** to log you out when you log in with SSH. When try to connect to the shell at bandit18, it presented with an error message.

![capture49](https://cloud.githubusercontent.com/assets/12239510/7899222/a5fb97b8-0739-11e5-9846-8e4adfb7f303.jpg)

Since it says that the password for the next level is stored inside a file called **readme** in the home directory, use **cat** command and read the content of the file to the stdout. 

![capture50](https://cloud.githubusercontent.com/assets/12239510/7899221/a5f1ddfe-0739-11e5-9549-3d4b6710f516.jpg)

	username: bandit19
	password: IueksS7Ubh8G3DCwVzrTd8rAVOwq3M5x

![capture51](https://cloud.githubusercontent.com/assets/12239510/7899223/a6066580-0739-11e5-95bd-0ba607a35740.JPG)


###Level 19 -> Level 20###
To gain access to the next level, you should use the **setuid** binary in the home directory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (**/etc/bandit_pass**), after you have used to **setuid** binary.

> **setuid** and **setgid** (short for "set user ID upon execution" and "set group ID upon execution", respectively) are Unix access rights flags that allow users to run an executable with the permissions of the executable's owner or group respectively and to change behaviour in directories. They are often used to allow users on a computer system to run programs with temporarily elevated privileges in order to perform a specific task. While the assumed user id or group id privileges provided are not always elevated, at a minimum they are specific.

By running the binary with shows the usage of the binary and gives an example of using the id command. Running the binary with the **id** command as the argument shows that it runs with the effective user and group id of **bandit20**, which means it runs with privileges of **bandit20**. When the binary runs with the **whoami** it shows the effective user of the current terminal as **bandit20**. So we can use **cat** command to read the password of the next level with the binary.

![capture52](https://cloud.githubusercontent.com/assets/12239510/7899224/a6137aae-0739-11e5-8274-47ca803670c0.JPG)

	username: bandit20
	password: GbKksEFF4yrVs6il55v6gwY5aVje5f0j

![capture53](https://cloud.githubusercontent.com/assets/12239510/7899225/a61b9806-0739-11e5-9e83-20f0dbb7b05f.JPG)


###Level 20 -> Level 21###
There is a **setuid** binary in the home directory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

**NOTE**: To beat this level, you need to login twice: once to run the **setuid **command, and once to start a network daemon to which the **setuid** will connect.

**NOTE 2**: Try connecting to your own network daemon to see if it works as you think.

![capture54](https://cloud.githubusercontent.com/assets/12239510/7899226/a6249578-0739-11e5-94b0-74772e17d3af.JPG)

Using **nc** command and create a listening on a random port, and connect it with **suconnect** binary.

	**-l** --> Used to specify that **nc** should listen for an incoming connection rather than initiate a connection to a remote host.

![capture55](https://cloud.githubusercontent.com/assets/12239510/7899227/a62fcdee-0739-11e5-905e-b0f7e1c6ec44.JPG)

Then in a different shell connect with **suconnect**. Then we send the password of bandit20 through the nc session and suconnect sends back the new password.

![capture56](https://cloud.githubusercontent.com/assets/12239510/7899228/a63c8002-0739-11e5-9e52-850f671fd839.JPG)

![capture57](https://cloud.githubusercontent.com/assets/12239510/7899229/a647a55e-0739-11e5-8676-dde0210617e4.JPG)

	username: bandit21
	password: gE269g2h3mw3pwgrj0Ha9Uoqen1c9DGr

![capture58](https://cloud.githubusercontent.com/assets/12239510/7899230/a6517868-0739-11e5-9cbd-1078f0281174.JPG)


###Level 21 -> Level 22###
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

> **Cron** is a software utility, a time-based job scheduler in Unix-like computer operating systems. People who set up and maintain software environments use **cron** to schedule jobs (commands or shell scripts) to run periodically at fixed times, dates, or intervals. It typically automates system maintenance or administration—though its general-purpose nature makes it useful for things like connecting to the Internet and downloading email at regular intervals. Cron is driven by a ***crontab*** (cron table) file, a configuration file that specifies shell commands to run periodically on a given schedule. The crontab files are stored where the lists of jobs and other instructions to the cron daemon are kept. Users can have their own individual crontab files and often there is a system wide crontab file (usually in /etc or a subdirectory of /etc) that only system administrators can edit. Each line of a crontab file represents a job, and is composed of a CRON expression, followed by a shell command to execute.

![capture59](https://cloud.githubusercontent.com/assets/12239510/7899231/a65fe362-0739-11e5-9762-b4a06ecdd6ee.JPG)

	username: bandit22
	password: Yk7owGAcWjwMVRwrTesJEwB7WVOiILLI

![capture60](https://cloud.githubusercontent.com/assets/12239510/7899232/a6681fdc-0739-11e5-9882-2d070374847b.JPG)


###Level 22 -> Level 23###
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE**: Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.

![capture61](https://cloud.githubusercontent.com/assets/12239510/7899233/a673bacc-0739-11e5-9b90-9ebc8e33caa1.JPG)

We need to replace *$myname* with **bandit23**, and *$mytarget* with the return value. **Cron** creates a file in **/tmp** that is the result of an *md5 hashing process* combined with a username which creates the name of the file that will hold the password.

	username: bandit23
	password: jc1udXuA1tiHqjIsL8yaapX5XIAI6i0n

![capture62](https://cloud.githubusercontent.com/assets/12239510/7899234/a67fb296-0739-11e5-9439-f52d1431c225.JPG)


###Level 23 -> Level 24###
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE**: This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

**NOTE 2**: Keep in mind that your shell script is removed once executed, so you may want to keep a copy around.

![capture63](https://cloud.githubusercontent.com/assets/12239510/7899235/a68b02a4-0739-11e5-962e-4772a9b3ece6.JPG)

![capture64](https://cloud.githubusercontent.com/assets/12239510/7899236/a6971c24-0739-11e5-979c-ab58cec9ec8a.JPG)

The script has been modified since the last time by adding **timeout -s 9 60 "./$i"**. Therefore after copying the script to **/var/spool/bandit24** you have to wait at least ten minutes for the script to get executed by cron.

![capture65](https://cloud.githubusercontent.com/assets/12239510/7899237/a6a2b87c-0739-11e5-83e7-25f08f18c797.JPG)

	username: bandit24
	password: UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ

![capture66](https://cloud.githubusercontent.com/assets/12239510/7899238/a6a98e0e-0739-11e5-81fc-0466ecc12e1b.JPG)


###Level 24 -> Level 25###
A daemon is listening on port 30002 and will give you the password for **bandit25** if given the password for **bandit24** and a *secret numeric 4-digit pincode*. There is no way to retrieve the pincode except by going through all of the 10000 combinaties, called brute-forcing.

![capture67](https://cloud.githubusercontent.com/assets/12239510/7899239/a6b65b16-0739-11e5-9508-466ea87705aa.JPG)

Since the 4-digit pin code can vary from 0001-9999; write a script to automate the process.

![capture68](https://cloud.githubusercontent.com/assets/12239510/7899240/a6c23bac-0739-11e5-9dc6-8df8752bc8f6.JPG)

![capture69](https://cloud.githubusercontent.com/assets/12239510/7899241/a6cc60fa-0739-11e5-9424-bc76d3e75db0.JPG)

	username: bandit25
	password: uNG9O58gUE7snukf3bvZ0rxhtnjzSGzG

![capture70](https://cloud.githubusercontent.com/assets/12239510/7899242/a6da2906-0739-11e5-9e09-52ef3ad5b781.JPG)


###Level 25 -> Level 26###
Logging in to **bandit26** from bandit25 should be fairly easy… The shell for user bandit26 is ***not* /bin/bash**, but something else. Find out what it is, how it works and how to break out of it.

![capture71](https://cloud.githubusercontent.com/assets/12239510/7899243/a6e3efae-0739-11e5-89ff-26055176459b.JPG)

![capture72](https://cloud.githubusercontent.com/assets/12239510/7899244/a6ec87e0-0739-11e5-918b-933df79855d3.JPG)

![capture73](https://cloud.githubusercontent.com/assets/12239510/7899245/a6f773b2-0739-11e5-9fd4-39e0fce49031.JPG)

![capture74](https://cloud.githubusercontent.com/assets/12239510/7899246/a7018eec-0739-11e5-88c5-6ff9f0accd7a.JPG)

Adjust the window to a very small scale where you see “--More--” at the bottom.

![capture75](https://cloud.githubusercontent.com/assets/12239510/7899247/a70ffd56-0739-11e5-91b1-e02411e46c02.JPG)

Then press '**v**'.

![capture76](https://cloud.githubusercontent.com/assets/12239510/7899248/a71c46ec-0739-11e5-9a1d-1e666263222a.JPG)

![capture77](https://cloud.githubusercontent.com/assets/12239510/7899249/a7248ef6-0739-11e5-9f42-9ea75a959ed1.JPG)

![capture78](https://cloud.githubusercontent.com/assets/12239510/7899250/a72ea7ba-0739-11e5-972b-0ed618055ff0.JPG)

	username: bandit26
	password: 5czgV9L3Xx8JPOyRbXh6lQbmIOWvPT6Z


###Level 26 -> Level 27###
At this moment, level 27 does not exist yet.

