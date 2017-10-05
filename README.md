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
isolinux.cfg file
change This lines with:
label linux
  menu label ^Install CentOS 7
  kernel vmlinuz
  append initrd=initrd.img inst.stage2=hd:LABEL=CentOS\x207\x20x86_64 quiet

label check
  menu label Test this ^media & install CentOS 7
  menu default
  kernel vmlinuz
  append initrd=initrd.img inst.stage2=hd:LABEL=CentOS\x207\x20x86_64 rd.live.check quiet

TO
label Linux
  menu label ^Install CentOS 7
  menu default 
  kernel vmlinuz
  append initrd=initrd.img ks=cdrom:/ks.cfg

label check
  menu label Test this ^media & install CentOS 7
  kernel vmlinuz
  append initrd=initrd.img ks=cdrom:/ks.cfg LABEL=CentOsx7_SMBx64 rd.live.check quiet


9)Give path of kickstart file for installation of operating system.

10)Build iso file of the /cent folder.:

Building iso file command :

genisoimage -untranslated-filenames -volid 'CentOS 7 x86_64' -J -joliet-long -rational-rock -translation-table -input-charset utf-8 -x  ./lost+found -b isolinux/isolinux.bin -c isolinux/boot.cat -no-emul-boot -boot-load-size 4 -boot-info-table -eltorito-alt-boot -e images/efiboot.img  -no-emul-boot -o /(destination path)/CentOS7_SMB.iso -T /(sorce path)/cent/



11)Burn the iso file to  blanck DVD.

12)Finally run the DVD.

