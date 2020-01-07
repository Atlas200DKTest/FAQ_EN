# How Do I Configure the Developer Board to Connect to the Network Through the  Mind Studio  Server in USB Connection Mode?<a name="EN-US_TOPIC_0196221460"></a>

Configure a routing rule on the  Mind Studio  server to allow the forwarding of IP packets from the developer board.

The IP address of the  Mind Studio  server must be configured on the developer board.

The following describes the detailed configurations on the  Mind Studio  server and on the developer board, respectively.

## Configurations on the  Mind Studio  Server \(UI Host\)<a name="section11475181982012"></a>

Run the following command as the  **root**  user:

1.  Enable packet forwarding.

    **echo "1" \> /proc/sys/net/ipv4/ip\_forward**

2.  Configure NAT.

    **sudo iptables -t nat -A POSTROUTING -o enp2s0 -s 192.168.1.0/24 -j MASQUERADE**

    **enp2s0**  indicates the NIC connected to the external network.  **-s**  indicates that only the IP packets from the developer board are forwarded.  **192.168.1.0/24**  indicates the IP addresses within the network segment 192.168.1.0–192.168.1.24. The IP address of the developer board must be in this network segment.

3.  Configure forwarding rules.

    **sudo iptables -A FORWARD -i enp0s20f0u8 -o enp2s0 -m state --state RELATED,ESTABLISHED -j ACCEPT**

    **sudo iptables -A FORWARD -i enp0s20f0u8 -o enp2s0 -j ACCEPT**

    **enp0s20f0u8**  indicates the USB virtual NIC on the uihost, which indicates the entry of data packets.


## Configurations on the Developer Board<a name="section452501217266"></a>

1.  Configure a default route.

    **sudo ip route change default via 192.168.1.251 dev usb0**

    In the preceding command,  **192.168.1.251**  is the IP address of the NIC for the  Mind Studio  server to connect to the developer board. You can run the ifconfig command to view the IP address.

    >![](public_sys-resources/icon-note.gif) **NOTE:**   
    >If "TNELINK answers: No such file or directory" is displayed during the execution of the  **ifconfig**  command, it indicates that the route exists on the developer board. In this situation, change the route address. For example, modify the command to the following:  
    >**sudo ip route add default via 192.168.1.251 dev usb0**  

2.  Add a DNS on the developer board.

    **sudo vi /etc/resolvconf/resolv.conf.d/base**

    Add the following command:

    **nameserver 114.114.114.114**

    Run the  **:wq**  command to save the configuration and exit.

3.  Run the following command for the configuration to take effect:

    **resolvconf -u**

    You can run the  **cat /etc/resolv.conf**  command to confirm the file content.


