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


