<!-- You have some errors, warnings, or alerts. If you are using reckless mode, turn it off to see inline alerts.
* ERRORs: 0
* WARNINGs: 0
* ALERTS: 5 -->

**Lab 1**

 1. Use systemctl to view the status of all the system services.

 systemctl status


2. Change the default run level back to multi-user.target and reboot.
sudo systemctl get-default

systemctl set-default multi-user
sudo reboot -i 
systemctl set-default graphical.target 


1. Send mail to the root user.

    $ echo "ezyek ya root" | mailx -s "hello root" root

1. Verify that you have received this mail.

    eirloom Mail version 12.5 7/5/10. Type ? for help.


    "/var/spool/mail/root": 1 message 1 new



1. Use `systemctl `utility to stop `postfix` service

    $ systemctl stop postfix

1. Send mail again to the root user.

    $ echo "azayk tany yact" | mailx -s"hello again ya root" root

1. Verify that you have received this mail.

    NO

1. Use `systemctl` utility to start `postfix` service

    $ systemctl start postfix

1. Verify that you have received this mail.

    Yes


Heirloom Mail version 12.5 7/5/10. Type ? for help.

"/var/spool/mail/root": 2 messages 1 new 2 unread


>N 2 root Wed Dec 7 14:01 18/608 "hello again ya root"

&



1. Edit in the GRUB2 configuration file and change the timeout variable equal 20 seconds.

    Sudo vi _etc/_default/grub



###############IMAGE###############IMAGE3.png "###############IMAGE_tooltip")




1. Edit in the GRUB2 configuration file and change your default operating system

GRUB_TIMEOUT=20

GRUB_DISTRIBUTOR="$(sed 's, release .*$,,g' /etc/system-release)"

GRUB_DEFAULT=0

GRUB_DISABLE_SUBMENU=true

GRUB_TERMINAL_OUTPUT="console"

GRUB_CMDLINE_LINUX="resume=/dev/mapper/rhel-swap rd.lvm.lv=rhel/root rd.lvm.lv=rhel/swap rhgb quiet"

GRUB_DISABLE_RECOVERY="true"

GRUB_ENABLE_BLSCFG=true

$ sudo grub2-mkconfig -o bootgrub2/grub.cfg



1. Install a new printer called "tty12" using web utility. Have the printer queue be "/dev/tty12" and specify a "Text Only Printer" for its model type.

    $ sudo usermod -a -G sys reem



###############IMAGE###############IMAGE4.png "###############IMAGE_tooltip")




1. P rint the file /etc/hosts to the printer and view the /dev/tty12 console to ensure that the print job went to the "printer".

    $ lp /etc/hosts


    request id is tty12-1 (1 file(s))


    $ sudo cat /dev/tty12


    $ lpq


    tty12 is ready and printing

1. Prevent jobs from leaving the tty12 printer queue to the printer. Do not prevent users from sending jobs to the tty12 printer queue.

    disable tty12

1. Print three files (/etc/hosts, /etc/xinetd.conf, and /etc/hosts.allow) to the tty12 printer

    lp: Error - unable to access "/etc/hosts.allow" - No such file or directory

1. View the print queue.

    $ lpq

1. Remove the second print job from the tty12 printer queue, and then allow the print jobs from the queue to be printed

    $ lpq {get job id}


    $ lprm tty12-1

1. Prevent print jobs from going to the tty12 printer's print queue.
1. Verify this by trying to print the /etc/hosts file.
1. Delete the tty12 printer with the lpadmin command.

    $ lpadmin -x tty12

1. You want to know some information about the status of the system every ten minutes today between the hours of 8:00 AM and 5:00 PM. to help investigate some performance issues you have been having. You suspect it might be memory related and want to keep an eye on those resources.

*/10 8-17 8 12 4 systemctl status



1. Use mail as the root user to check for e-mail from the cron jobs you have scheduled.


###############IMAGE###############IMAGE5.png "###############IMAGE_tooltip")




1. How could you send the output from these cron jobs to another e-mail address (the manager user)?

MAILTO="user.one@domain.one,user.two@domain.two"



1. Use mail as the manager user to check for e-mail from the cron jobs you have scheduled.

    mailx
