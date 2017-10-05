# Unattended-INstallation-of-SAMBA-using-Kickstart
Installing and configuring  SAMBA server using Kickstart Open-source tool 
<h5>REQUIREMENTS/<h5> :
Linux based OS iso file( I used CENTos7)
Kickstart configurator

#STEPS :
1)Create a kickstart file using kickstart configurator.

2)write post installation script in the kickstart file to install and configure samba server.

3)Add necessary package and group name into kickstart file.

4)Mount the Centos7-dvd.iso to pc.

5)Create a folder /cent

6)Copy all the contains from mounted iso including hidden folder (.treeinfo & .diskinfo) to  /cent folder

7)Put the kickstart file  into the /cent folder.

8)Open isolinux.cfg from isolinux folder.

9)Give path of kickstart file for installation of operating system.

10)Build iso file of the /cent folder.

11)Burn the iso file to  blanck DVD.

12)Finally run the DVD.

