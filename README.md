# renamejoin

Tool for automatic rename windows 10 and join it to microsoft domain 

#prepare deployment windows to rolling out

1) install netdom on deployment windows from install_netdom_url.txt
2) change domain.local  Joinadmin  and password1234QWE in file step2.cmd to your own
3) move all files to c:\renamejoin\ on deployment windows
4) run command from createtesk.txt as admin on deployment windows

#rolling out
create image deployment windows and deploy it to target computers


#how it works

1) windows run task on boot file C:\renamejoin\step1.cmd
it rename computer to win-%random%, reboot it, delete C:\renamejoin\step1.cmd and rename C:\renamejoin\step2.cmd to C:\renamejoin\step1.cmd
2) windows boot second time and run on boot file C:\renamejoin\step1.cmd
it join windows to domain, reboot it, and delete C:\renamejoin\step1.cmd
