# What Do I Do If the UI Host That Connects to the Developer Board in USB Mode Fails to Connect to the Network?<a name="EN-US_TOPIC_0196221408"></a>

## Symptom<a name="section1238712155617"></a>

The developer board is connected to the network through the UI Host according to  [How Do I Configure the Developer Board to Connect to the Network Through the Mind Studio Server in USB Connection Mode?](how-do-i-configure-the-developer-board-to-connect-to-the-network-through-the-mind-studio-server-in-u.md).

The information configured on the UI Host becomes invalid after the system is restarted.

Similarly, the default route \(**sudo ip route change default via 192.168.1.251 dev usb0**\) configured on the developer board becomes invalid each time the developer board is restarted.

## Solution<a name="section018510184572"></a>

-   For the issue that configuration on the  Mind Studio  UI Host becomes invalid after restart:
    -   If the values configured in the  **ip\_forward**  file using  **echo "1" \> /proc/sys/net/ipv4/ip\_forward**  in Step 1, perform the following steps:

        Remove the comment of the  **net.ipv4.ip\_forward=1**  line in the  **/etc/sysctl.conf**  file. Run the  **sysctl -p**  command. The configurations in the  **/proc/sys/net/ipv4/ip\_forward**  file will still be valid after the restart.

    -   If the iptables configuration of the NAT and forwarding rules in UI Host in  [2](how-do-i-configure-the-developer-board-to-connect-to-the-network-through-the-mind-studio-server-in-u.md#li187110388231)  and  [3](how-do-i-configure-the-developer-board-to-connect-to-the-network-through-the-mind-studio-server-in-u.md#li91171427162410)  becomes invalid, perform the following steps:

        Run the following command to install iptables-persistent:

        **sudo apt-get install iptables-persistent**

        Then, reconfigure the NAT and forwarding rules by referring to  [2](how-do-i-configure-the-developer-board-to-connect-to-the-network-through-the-mind-studio-server-in-u.md#li187110388231)  and  [3](how-do-i-configure-the-developer-board-to-connect-to-the-network-through-the-mind-studio-server-in-u.md#li91171427162410).

        After the configuration, run the following command to save the configured rules to the  **/etc/iptables/rules.v4**  and  **/etc/iptables/rules.v6**  files:

        **sudo netfilter-persistent save**

        Each time the system restarts, the  **sudo netfilter-persistent reload**  command is automatically executed to enable the saved iptables rules. You can run the  **sudo iptables -nvL --line-number**  command to view the saved iptables rules.


-   If the default route configuration on the developer board becomes invalid after restart, perform the following operation:

    Add  **sudo ip route change default via  _192.168.1.251_  dev usb0**  before  **exit 0**  in the  **/etc/rc.local**  file.

    In the preceding command,  **192.168.1.251**  is the IP address of the NIC for the  Mind Studio  server to connect to the developer board. You can run the  **ifconfig **command to view the IP address. For details, see  [1](how-do-i-configure-the-developer-board-to-connect-to-the-network-through-the-mind-studio-server-in-u.md#li209271728102611).


