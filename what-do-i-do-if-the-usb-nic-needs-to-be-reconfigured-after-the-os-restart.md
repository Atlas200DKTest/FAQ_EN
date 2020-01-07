# What Do I Do If the USB NIC Needs to Be Reconfigured After the OS Restart?<a name="EN-US_TOPIC_0197153490"></a>

## Description<a name="section1369911589264"></a>

In some environments, after the Ubuntu host or the Atlas 200 DK is restarted, the USB NIC needs to be reconfigured. When the host is restarted, the USB NIC configuration information exists, but the IP address of the USB NIC does not take effect. The previous IP address needs to be deleted and needs reconfiguring. Is there any solution?

## Solution<a name="section01939562286"></a>

The configuration information exists in the network configuration file, so you only need to run the following command to restart the NIC instead of configuring a new IP address:

**sudo service network-manager restart**

After the restart, run the  **ifconfig -a **command to check whether the IP address of the USB virtual NIC is displayed.

