Lab_3 admin_2
1. Display your MAC address by 2 different ways.


2. Display the network settings of all active interfaces.

3. Display the network setting of all interfaces both active inactive.

4. Bring your interface down.

5. Configure your network card to have static IP.

6. Bring your interface up. && 7. Verify your network setting using ifconfig command

8. Configure your network card to have dynamic IP using network manager command.

9. Check using ifconfig then check its configuration file.

10. Reconfigure your network card using system-config-network utility to have static IP.

11. Configure your network card to have 3 IPs and check that they are all working using ifconfig command.


12. Change your host name in your global network file.

13. Check the present value of /proc/sys/net/ipv4/icmp_echo_ignore_all

14. It should be 0, change it to 1 which will prevent other hosts from successfully pinging your host while not affecting your ability to ping them.

15. Try to ping your colleague, let your colleague try to ping your host.
16. Reboot and try the last step. What happened? Why?

17. Edit /etc/sysctl.conf and put the following line at the bottom:
net.ipv4.icmp_echo_ignore_all=1
18. Execute sysctl –p command.
19. Check the value of /proc/sys/net/ipv4/icmp_echo_ignore_all.







Using yum
20. Attempt to run the command gnuplot. You should find that it is not installed.
21. Search for the plotting packages.
22. Find out more information about the gunuplot package.
23. Install the gnuplot package.
24. Attempt to remove the gnuplot package, but say no How many packages would be removed
25. Attempt to remove the gunplot-common package but say no How many packages would be removed Using rpm

26. List all installed packages in your system.
27. View the files in the initscripts package
28. Get general information about bash rpm.
29. Have the files from the pam package changed since it was installed.
30. Which installed packages have gnome in their names?
31. Install any uninstalled package from RH Enterprise Linux cds
32. Search for software resemble the Photoshop software other than Gimp and install it.
33. Create the file /etc/yum.repos.d/cdrom.repo to enable install from the iso from the iso of Red Hat.
34. Try to install any package from the new repository