# How Do I Deploy  Mind Studio  or the Atlas 200 DK Dependencies Offline?<a name="EN-US_TOPIC_0196221467"></a>

## Context<a name="section109741724131114"></a>

If the Ubuntu server cannot connect to the network,  Mind Studio  or the cross compilation environment dependencies of the Atlas 200 DK cannot be installed online \(for example: gcc g++ cmake curl libboost-all-dev libatlas-base-dev unzip haveged liblmdb-dev qemu-user-static binfmt-support python3-yaml gcc-aarch64-linux-gnu g++-aarch64-linux-gnu\). For details about the dependencies, see  _Ascend 310 Mind Studio Installation Guide \(Ubuntu, x86\)_  and  _Ascend 310 Atlas 200 Developer Kit User Guide_. In this case, you need to deploy the dependencies offline.

## Procedure<a name="section1362910751518"></a>

1.  <a name="li699981461510"></a>On a Ubuntu 16.04.3 server that is connected to the network, install the required software online by referring to  _Ascend 310 Mind Studio Installation Guide \(Ubuntu, x86\)_  and  _Ascend 310 Atlas 200 Developer Kit User Guide_.

    For example, run the  **apt-get install gcc-aarch64-linux-gnu**  command to install the cross compiler.

    After the software is downloaded online, you can obtain the .deb packages of the software from the  **/var/cache/apt/archives**  directory on the Ubuntu server that is connected to the network.

2.  Upload the .deb packages obtained in  [1](#li699981461510)  to any directory on the  Mind Studio  Ubuntu server as the  Mind Studio  installation user.
3.  <a name="li2496165217342"></a>Run the following command to install the .deb packages.

    **sudo dpkg -i deb  _software package name_**

    >![](public_sys-resources/icon-note.gif) **NOTE:**   
    >If dependency packages need to be deployed during the installation, deploy the dependency packages on the Ubuntu server where  Mind Studio  is located by referring to  [1](#li699981461510)–[3](#li2496165217342), and then install the .deb packages.  


