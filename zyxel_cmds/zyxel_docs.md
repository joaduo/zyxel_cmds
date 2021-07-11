
How do I set port forwarding rule by CLI command on my CPE?

Answer

Follow the steps below and you can set a port forwarding rule on your P660H-D1:
ras> ip nat server load 1
ras> ip nat server edit 2
 

clear active svrport intport and remotehost leasetime rulename forwardip protocol
ras> ip nat server edit 2 active yes
active = 1
ras> ip nat server edit 2 svrport 2525 2525
ras> ip nat server edit 2 intport 25 25
ras> ip nat server edit 2 rulename lenatest
ras> ip nat server edit 2 forwardip 192.168.1.100
ras> ip nat server edit 2 protocol TCP
ras> ip nat server save

In this example,my server ip address and port is 192.168.1.100/25, and I forwarded my tcp port 25 to port 2525, You can change it according your needs.
Here, you can use rule 2 to 12, rule 13 to 24 is special for upnp.
After you finished setting, you can use command 'ip nat server disp' to check your port forwarding pool.

Note: These commands are supported by firmware 340AGD2C0.
