# What Do I Do If a Redundant Mounted Disk Appears Due to Manual Removal of the SD Card During SD Card Creation?<a name="EN-US_TOPIC_0196221499"></a>

If the SD card is manually removed during SD card creation a redundant temporarily mounted disk is generated. You can perform the following steps to remove it.

1.  <a name="en-us_topic_0177457208_li1139413655815"></a>Log in to the Ubuntu server where  Mind Studio  is located as the  Mind Studio  installation user and run the  **su - root**  command to switch to the  **root **user.
2.  <a name="en-us_topic_0177457208_li15906541188"></a>Run the  **df -h**  command to view the temporarily mounted  **/dev/loop0**  disk.

    ```
    root@kickseed:~# df -h
    Filesystem       Size     Used      Avail   Use% Mounted on
    /dev/loop0      745M  745M     0        100% /home/ubuntu/studio/scripts/180919002200
    /dev/sdc1        118G   60M       112G  1%    /home/ubuntu/studio/scripts/sd_mount_dir
    ```

3.  <a name="en-us_topic_0177457208_li143961867582"></a>Run the  **umount**  command to unmount the disk. Replace  _/dev/loop0_  and  _/dev/sdc1_  in the commands based on the actual query result in  [2](#en-us_topic_0177457208_li15906541188).

    ```
    root@kickseed:~# umount /dev/loop0
    root@kickseed:~# umount /dev/sdc1
    ```

    If "target is busy" is displayed, restart the Ubuntu PC and repeat  [1](#en-us_topic_0177457208_li1139413655815)  to  [3](#en-us_topic_0177457208_li143961867582).


