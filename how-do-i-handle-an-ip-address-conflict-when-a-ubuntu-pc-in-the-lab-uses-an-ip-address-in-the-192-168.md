# How Do I Handle an IP Address Conflict When a Ubuntu PC in the Lab Uses an IP Address in the 192.168.1.xx Network Segment to Access the Network?<a name="EN-US_TOPIC_0196221442"></a>

## Symptom<a name="section1385103710301"></a>

Currently, PCs or servers in many LANs are configured with IP addresses in the 192.168.1.xxx network segment, and the IP addresses are automatically allocated. Therefore, if they connect to the developer board in USB mode, the IP address of the developer board is in the 192.168.1.xxx network segment by default. As a result, the IP address of the USB virtual NIC on the PC must also reside in the 192.168.1.xxx network segment, otherwise, an IP address conflict is likely to occur.

## Solution<a name="section780018823311"></a>

1.  Remove the network cable from the Ubuntu PC where  Mind Studio  is located \(to avoid the IP address conflict\), connect the PC to the developer board over the USB port, and log in to the developer board \(192.168.1.2\) as the  **HwHiAiUser**  user.
2.  Switch to the  **root**  user on the developer board, change the static IP address of the USB0 NIC to another network segment, for example, 192.168.2.xxx, and modify  **/etc/network/interface**  as follows:

    ```
    auto usb0
    iface usb0 inet static
    address 192.168.2.2
    netmask 255.255.255.0
    ```

    In the preceding example, the IP address of the developer board is set to  **192.168.2.2**.

3.  Power off the developer board and power it on again to enable the new IP address of the USB0 NIC on the developer board to take effect. In this situation, set the IP address of the USB virtual NIC in Ubuntu to  **192.168.2.**_**xxx**_, for example,  **192.168.2.134**.
4.  After the network cable is connected to the Ubuntu PC, the IP address conflict disappears.

