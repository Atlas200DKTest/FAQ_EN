# What Do I Do If the Developer Board Fails to Connect to  Mind Studio  in USB Mode?<a name="EN-US_TOPIC_0196221465"></a>

## Description<a name="section95868574446"></a>

The connection failure persists even after a user refers to  **Configuring the Atlas 200 DK \> Connecting the Atlas 200 DK Developer Board to  Mind Studio**  in  _Ascend 310 Atlas 200 Developer Kit User Guide_.

## Solution<a name="section1824414459461"></a>

1.  Check the environment.
    -   If the Ubuntu OS is deployed using VMware or VirtualBox on a Windows PC, ensure that the developer board is connected to the VM instead of the Windows OS through the USB port. When the developer board is connected to the USB port of the PC, a dialog box is displayed, asking whether to connect the device to the Windows or VM. At this time, select the VM. If no dialog box is displayed, check whether the VM is configured to be compatible with USB 3.0. If not, perform the configuration.
    -   If the Ubuntu OS or the USB port has been connected to the VM on the PC, perform the following operations:
        -   Check whether the developer board is powered on. If not, power on the board.
        -   If the developer board is powered on, run the  **ifconfig -a**  command to check whether the virtual NIC in the Ubuntu OS is started. If it is not started, go to  [2](#li7513753125019).

2.  <a name="li7513753125019"></a>Perform the following operations if the virtual NIC is not started:

    If the LED indicator is lit properly but the virtual NIC is still unavailable after power-on, it is suspected that the USB port or data cable is faulty. In this case, use a network cable for connection.

    If the connection is successful, end the troubleshooting. Otherwise, go to  [3](#li144935588522).

3.  <a name="li144935588522"></a>Perform the following operations if the virtual NIC is started but is not bound to an IP address:
    1.  In the  **/etc/network/interfaces**  file, check whether the IP address of the virtual NIC is configured correctly. Check whether the NIC name and IP address are the same as the virtual NIC name and IP address in the  **ifconfig -a**  command output, whether the IP address is correctly configured, and whether the IP address is in the same network segment as  **192.168.1.2**.
    2.  If the IP address of the virtual NIC is not configured in the  **/etc/network/interfaces**  file, configure one by referring to the description about how to configure an IP address for the  Mind Studio  server in  **Configuring the Atlas 200 DK \> Connecting the Atlas 200 DK Developer Board to  Mind Studio**  in  _Ascend 310 Atlas 200 Developer Kit User Guide_  and change  **managed=false**  in the  **NetworkManager.conf**  file to  **managed=true**.
    3.  If the IP address still takes effect, switch to the  **root**  user and run the following commands:

        **ifdown NIC name**

        **ifup NIC name**

        **service networking restart**

        **service NetworkManager restart**

    4.  Run the  **ifconfig -a**  command to check whether the IP address takes effect and ping  **192.168.1.2**. If the IP address fails to be pinged, go to  [4](#li2571164618576).

4.  <a name="li2571164618576"></a>Perform the following operations if both the virtual NIC and the static IP address of the NIC take effect but the developer board's IP address \(192.168.1.2\) fails to be pinged:
    1.  If the network segment of Ubuntu Server is  **192.168.1.**_x_, an IP address conflict may occur. For details, see  [https://bbs.huaweicloud.com/forum/thread-16966-1-1.html](https://bbs.huaweicloud.com/forum/thread-16966-1-1.html).
    2.  The default static IP address of USB0 on the developer board may be changed to a value other than  **192.168.1.2**. In this situation, try other common network segments, use a network cable for connection and check the default IP address of USB0, or refer to  [4.c](#li10431118013).
    3.  <a name="li10431118013"></a>If the default IP address of USB0 on the developer board does not take effect due to a developer board fault, use a network cable to set up the connection if possible. If using a network cable to set up the connection fails, use a serial cable instead and check whether the IP address takes effect based on the  **ifconfig -a**  command output. For details, see  [https://bbs.huaweicloud.com/forum/thread-16962-1-1.html](https://bbs.huaweicloud.com/forum/thread-16962-1-1.html). If the IP address does not take effect, check the serial port startup log and send the log to Huawei engineers to locate the fault.


