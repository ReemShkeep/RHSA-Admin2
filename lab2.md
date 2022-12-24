Lab 2
    1. Using the useradd command, add accounts for the following users in your system: user1, user2, user3, user4, user5, user6 and user7. Remember to give each user a password.


![Screenshot from 2022-12-04 03-07-45](https://user-images.githubusercontent.com/96814665/209441348-e85c4e9d-ca84-4d19-ad4d-c8d4f77dc809.png)



![Screenshot from 2022-12-04 03-10-56](https://user-images.githubusercontent.com/96814665/209441350-6965092a-38aa-48f9-b0e4-d941a33eb4e0.png)
![Screenshot from 2022-12-04 03-14-05](https://user-images.githubusercontent.com/96814665/209441455-5f4de467-9db2-441b-9de2-bb27de596158.png)


    2. Using the groupadd command, add the following groups to your system.
Group			GID
sales			10000
hr			10001
web			10002


![Screenshot from 2022-12-04 03-14-05](https://user-images.githubusercontent.com/96814665/209441357-a532ecab-559a-446e-9bf7-f063d94310d6.png)
![Screenshot from 2022-12-04 04-06-45](https://user-images.githubusercontent.com/96814665/209441616-ccfd94c7-1fd3-47ec-9e90-0a2b2a208dc3.png)


Why should you set GID in this manner instead of allowing the system to set the GID by default? 
##because the system will generate an incremental number not starting from 10000




    3. Using the usermod command to add user1 and user2 to the sales auxiliary group, user3 and user4 to the hr auxiliary group. User5 and user6 to web auxiliary group. And add user7 to all auxiliary groups  
![Screenshot from 2022-12-04 04-45-03](https://user-images.githubusercontent.com/96814665/209441507-d1ff2a2e-09da-45f0-bd48-43b2236114b3.png)






    4.  Login as each user and use id command to verify that they are in the appropriate groups. How else might you verify this information?![Screenshot from 2022-12-04 03-38-36](https://user-images.githubusercontent.com/96814665/209441380-ab2e2875-b881-46f5-95d8-39262f81245d.png)


    5. Create a directory called /depts with a sales, hr, and web directory within the /depts directory.
    ![Screenshot from 2022-12-04 03-42-16](https://user-images.githubusercontent.com/96814665/209441388-5e07f7a1-3065-45e1-8a40-0ba1f6b62a96.png)


    6. Using the chgrp command, set the group ownership of each directory to the group with the matching name

![Screenshot from 2022-12-04 04-45-03](https://user-images.githubusercontent.com/96814665/209441404-0dbe3ab4-bc94-4cef-a8d7-8a6e4e39b99f.png)

![Screenshot from 2022-12-04 04-45-33](https://user-images.githubusercontent.com/96814665/209441547-1d436fd5-778a-46b4-83df-cd01cbcf22c3.png)


![Screenshot from 2022-12-04 06-43-33](https://user-images.githubusercontent.com/96814665/209441525-af983d2f-4100-4388-939f-4977ad5aaa08.png)


    7. Set the permissions on the /depts directory to 755, and each subdirectory to 770

![Screenshot from 2022-12-04 04-45-33](https://user-images.githubusercontent.com/96814665/209441419-5a5a8a37-c49e-4958-9298-52422b28d814.png)


    8. Set the set-gid bit on each departmental directory











    9. Use the su command to switch to the user2 account and attempt the following commands:
touch /depts/sales/user2.txt
touch /depts/hr/ user2.txt
touch /depts/web/ user2.txt
![Screenshot from 2022-12-04 05-37-43](https://user-images.githubusercontent.com/96814665/209441565-ca1c6881-cb1e-4018-bb5e-8571252f1b07.png)

![Screenshot from 2022-12-04 05-49-15](https://user-images.githubusercontent.com/96814665/209441567-ec0cf4da-5e6e-4829-96f0-e30cdf1c0f8e.png)



Which of these commands succeeded and which failed? What is the group ownership of the files that were created?
Ans:- the ownership directory not the owner .

10. Configure sudoers file to allow user3 and user4 to use /bin/mount and /bin/umount commands, while allowing user5 only to use fdisk command.
    ![Screenshot from 2022-12-04 06-36-28](https://user-images.githubusercontent.com/96814665/209441627-caf54a0d-ebaa-45bf-96c8-72ed0d14c68f.png)

    ![Screenshot from 2022-12-04 06-37-48](https://user-images.githubusercontent.com/96814665/209441633-0d92af1b-e173-4c45-94f5-4d3259867143.png)

    
    11. Ans:-
		sudo visudo
		user3 ALL=(ALL) !ALL, /bin/mount, /bin/umount
		user4 ALL=(ALL) !ALL, /bin/mount, /bin/umount
		user5 ALL=(ALL) !ALL, /sbin/fdisk
    12. Login by user3 and try to unmount /boot.
		Ans:- sudo umount /dev/boot
    13. Login by user4 and remount /boot. Also try to view the partition table using fdisk.
		Ans:- fdisk /dev/boot
    14. Create a directory with permissions rwxrwx---, grant a second group (sales) r-x permissions
mkdir dir1
chmod 770 dir1
setfacl -m g:sales:rx ~/dir1
    15.  create a file on that directory and grant read and write to a second group (sales)




















    16. set the the owning group as the owning group of any newly created file in that directory.Grand your colleagues a collective directory called /opt/research, where they can store generated research results. Only members of group profs and grads should be able to create new files in the directory, and new file should have the following properties:
    • the directory should be owned by root
    • new files should be group owned by group grads
    • group profs should automatically have read/write access to new files
    • group interns should automatically have read only access to new files
    • other users should not be able to access the directory and its contents at all.
      
    • Bonus
      Your boss thinks it’s a great idea to have one central logging server. Satisfy his requirements 
      Hint:
      Set up rsyslogd on the "logging server" machine to accept logging messages from other machines.
      On the your "workstation", set up rsyslogd to send messages to the "logging server
      Test the new setup by using the logger command on the "workstation" to generate a log message
      Does the message appear in the "logging server's" /var/log/messages file?
      Why does this message also appear in the "workstation's" /var/log/messages file?
      How could you have the message only appear in the "logging server's" files?
