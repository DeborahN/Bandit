#Wargames#

A wargame (or war game) in hacking is a security challenge in which one must exploit or defend a vulnerability in a system or application or gain or prevent access to a computer system.

A wargame usually involves semantic URL attacks, knowledge-based authentication, password cracking, reverse engineering of software (mostly JavaScript, Adobe Flash, and assembly language), code injection, SQL injections, cross-site scripting, exploits, IP address spoofing, and other hacking techniques.

##Bandit##

###Level 0###
The goal of this level is for you to log into the game using SSH. The host to which you need to connect is **bandit.labs.overthewire.org**.  Using PuTTY session connect to the host.

![Capture1](https://lh6.googleusercontent.com/6M-WAOXl80RTo7HOQkanUyK4zFjfmfj3EVI2lkJXjScnsL-DNaVTcYBJ0-12QsL2HjAxry-Nz4LVzZEEFL6-7jBwcgeFMseWKyF7=w1342-h547)

	username: bandit0
	password: bandit0 

Once logged in, go to the Level 1 page to find out how to beat Level 1.

![Capture2](https://lh6.googleusercontent.com/8wFEucFYs6YQXRhJCH1Liv_Udy1Xbnx5UYHvwIUvj6ILdXE-x33kCbmKy6bnElWPnTuvvjbuCP6OQPA=w1342-h547)


###Level 0 -> Level 1###
The password for the next level is stored in a file called **readme** located in the home directory. Use this password to log into ***bandit1*** using SSH. Whenever you find a password for a level, use SSH to log into that level and continue the game. This level requires **ls** and **cat** commands to find *readme* file and to read the password.

![Capture3](https://lh3.googleusercontent.com/f21mknSEmevvJJxkfsNyBvquxwr8j8quDuLeS_sq9DTkC5s6BBDmzv8U4dYJT8f9JgV5BnwavtzUMQg=w1342-h547)

	username: bandit1
	password: boJ9jbbUNNfktd78OOpsqOltutMc3MY1

![Capture4](https://lh5.googleusercontent.com/CA4CUBjT6uKTjaZHztX6ySos9dc-jkimctOwsJEMOSWNHJOIaJ43mCJqBo8GFFpW3aKgfqQ0Dhk1t40=w1342-h547)


###Level 1 -> Level 2###
The password for the next level is stored in a file called **-** located in the home directory. 

We need to delimit the dash to read it, since it is a special character. With bash redirection, **-** is not recognised as a special filename, so bash will use that as the literal filename.  We have to specify that the file name is actually dash in the directory we are in. The usual way of doing this is to prefix the filename with a path **./-**

![Capture5](https://lh3.googleusercontent.com/mZ1FbU_qkbhm68RDC3papdMVVwZzGRtIzWOqUTdcOSCSy_WyCow8GxkVGOyTK-WiXCLTrfIQPoMn-98=w1342-h547)

	username: bandit2
	password: CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9

![Capture6]()


