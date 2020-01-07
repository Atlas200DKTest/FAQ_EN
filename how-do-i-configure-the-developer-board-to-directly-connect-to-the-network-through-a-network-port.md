# How Do I Configure the Developer Board to Directly Connect to the Network Through a Network Port?<a name="EN-US_TOPIC_0197337868"></a>

## Description<a name="section12157144045416"></a>

How can I connect the Atlas 200 DK developer board to the network through a network port instead of using the route forwarding mode?

## Solution<a name="section3271192405511"></a>

1.  Log in to the developer board, switch to the  **root **user, and open the  **interfaces **file.

    vim /etc/network/interfaces

2.  Configure the IP address obtaining mode of  **eth0 **to DHCP.

    ```
    auto eth0
    iface eth0 inet dhc
    ```

    Save and close the  **interfaces **file.

3.  Restart the developer board, and connect to the developer board through a USB port. Then, run the  **ifconfig **command to check whether the developer board has been assigned an IP address.

    ```
    HwHiAiUser@davinci-mini:~$ ifconfig
    eth0      Link encap:Ethernet  HWaddr 9a:28:91:80:fa:2f  
              inet addr:192.168.221.224  Bcast:192.168.221.255  Mask:255.255.254.0
              UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
              RX packets:27 errors:0 dropped:0 overruns:0 frame:0
              TX packets:15 errors:0 dropped:0 overruns:0 carrier:0
              collisions:0 txqueuelen:1000 
              RX bytes:2266 (2.2 KB)  TX bytes:2193 (2.1 KB)
              Interrupt:69 
    
    lo        Link encap:Local Loopback  
              inet addr:127.0.0.1  Mask:255.0.0.0
              UP LOOPBACK RUNNING  MTU:65536  Metric:1
              RX packets:160 errors:0 dropped:0 overruns:0 frame:0
              TX packets:160 errors:0 dropped:0 overruns:0 carrier:0
              collisions:0 txqueuelen:0 
              RX bytes:11840 (11.8 KB)  TX bytes:11840 (11.8 KB)
    
    usb0      Link encap:Ethernet  HWaddr fe:ef:37:29:76:7d  
              inet addr:192.168.1.2  Bcast:192.168.1.255  Mask:255.255.255.0
              UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
              RX packets:355 errors:0 dropped:45 overruns:0 frame:0
              TX packets:157 errors:0 dropped:0 overruns:0 carrier:0
              collisions:0 txqueuelen:1000 
              RX bytes:36914 (36.9 KB)  TX bytes:30407 (30.4 KB)
    ```

4.  Test the network connectivity.
    -   Run the  **ping www.baidu.com**  command to ping the IP address. The following information is displayed:

        ```
        HwHiAiUser@davinci-mini:~$ ping www.baidu.com
        PING www.a.shifen.com (112.80.248.76) 56(84) bytes of data.
        64 bytes from 112.80.248.76: icmp_seq=1 ttl=57 time=2.11 ms
        64 bytes from 112.80.248.76: icmp_seq=2 ttl=57 time=2.31 ms
        64 bytes from 112.80.248.76: icmp_seq=3 ttl=57 time=1.79 ms
        64 bytes from 112.80.248.76: icmp_seq=4 ttl=57 time=2.37 ms
        ^C
        --- www.a.shifen.com ping statistics ---
        4 packets transmitted, 4 received, 0% packet loss, time 3005ms
        rtt min/avg/max/mdev = 1.795/2.147/2.370/0.229 ms
        ```

    -   Alternatively, run the  **apt-get**  command. The following information is displayed:

        ```
        root@davinci-mini:/home/HwHiAiUser# apt-get update
        Get:1 http://ports.ubuntu.com/ubuntu-ports xenial InRelease [247 kB]
        Get:2 http://ports.ubuntu.com/ubuntu-ports xenial-security InRelease [109 kB]
        Get:3 http://ports.ubuntu.com/ubuntu-ports xenial-updates InRelease [109 kB]
        Get:4 http://ports.ubuntu.com/ubuntu-ports xenial/main arm64 Packages [1,130 kB]
        Get:5 http://ports.ubuntu.com/ubuntu-ports xenial/main Translation-en [568 kB]
        Get:6 http://ports.ubuntu.com/ubuntu-ports xenial-security/main arm64 Packages [480 kB]
        Get:7 http://ports.ubuntu.com/ubuntu-ports xenial-security/main Translation-en [291 kB]
        Get:8 http://ports.ubuntu.com/ubuntu-ports xenial-updates/main arm64 Packages [728 kB]
        Get:9 http://ports.ubuntu.com/ubuntu-ports xenial-updates/main Translation-en [402 kB]
        Fetched 4,064 kB in 4s (865 kB/s)                                    
        Reading package lists... Done
        ```



