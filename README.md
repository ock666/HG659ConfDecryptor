Reupload from the wayback machine
I also disabled cwmp for privacy reasons, just set cwmp=1 to cwmp=0.

# HG659ConfDecryptor

Thanks wassname100, Sandy P, Revs Per Min and solutionz at geekzone

Wassname's steps:
1. Login to the router
2. Open inspect element (Ctrl+Shift+I in Chrome), hit the 'Sources' tab, then open "lib/cat_exember.js.jgz" (mine had random code after the .jgz)
3. place a breakpoint on the top line (by clicking the number 1 in the left columns)
4. Reload the page. When it breaks, paste in the console "g_userLevel=2" and hit enter.
5. unpause. You will need to do this every time it breaks.
6. Go to Management>Device Management>"Backup and restore settings".

7. Place the newly downloaded 'downloadconfigfile.conf' in an accessible directory.

solutionz's steps:
8. Install Python (x64): https://www.python.org/ftp/python/2.6.6/python-2.6.6.amd64.msi
9.  Install Pycrypto (x64): http://www.voidspace.org.uk/downloads/pycrypto26/pycrypto-2.6.win-amd64-py2.6.exe
10.  Download "hg635_configtool.py":
11.  Put hg635_configtool.py in the same directory as downloadconfigfile.conf
12.  Open command prompt
13.  Navigate to the directory, and type 'hg635_configtool.py decrypt downloadconfigfile.conf output.xml' without the quotes

We now have an editable config file.

14.  From here, I found the following section:

<UserInfoInstance InstanceID="2" Username="admin" Userpassword="Ozgo8BYclaAK2X6zNJYepz1zqjFMhsmITvAGAMcsPcqA6uot79n1NnaGkC0Fkq/Widdyl29mxYwY9X2uROW3fGfZwL5HIGyxgEXIuMQxE+U=" Userlevel="1" UserpasswordSource="PPOLwiqNO3lE3enntnka4w==" EnablePasswdPrompt="0" UserpasswdPrompt=""/>

And changed "Userlevel=" to "2"

Finally,
15.  Save the config file, and go back to command prompt.
16.  Type 'hg635_configtool.py encrypt output.xml output.conf' (without quotes)
17.  Restore your settings: 192.168.1.1 > Maintain > Device Management > Backup or Restore Settings > Restore Settings > output.conf
