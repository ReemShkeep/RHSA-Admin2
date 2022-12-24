Lab 2
    1. Using the useradd command, add accounts for the following users in your system: user1, user2, user3, user4, user5, user6 and user7. Remember to give each user a password.







    2. Using the groupadd command, add the following groups to your system.
Group			GID
sales			10000
hr			10001
web			10002
Why should you set GID in this manner instead of allowing the system to set the GID by default? 
because the system will generate an incremental number not starting from 10000




    3. Using the usermod command to add user1 and user2 to the sales auxiliary group, user3 and user4 to the hr auxiliary group. User5 and user6 to web auxiliary group. And add user7 to all auxiliary groups  






    4.  Login as each user and use id command to verify that they are in the appropriate groups. How else might you verify this information?

    5. Create a directory called /depts with a sales, hr, and web directory within the /depts directory.

    6. Using the chgrp command, set the group ownership of each directory to the group with the matching name




    7. Set the permissions on the /depts directory to 755, and each subdirectory to 770



    8. Set the set-gid bit on each departmental directory











    9. Use the su command to switch to the user2 account and attempt the following commands:
touch /depts/sales/user2.txt
touch /depts/hr/ user2.txt
touch /depts/web/ user2.txt
Which of these commands succeeded and which failed? What is the group ownership of the files that were created?
Ans:- the ownership directory not the owner .

    10. Configure sudoers file to allow user3 and user4 to use /bin/mount and /bin/umount commands, while allowing user5 only to use fdisk command.
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