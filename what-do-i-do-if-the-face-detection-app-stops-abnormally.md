# What Do I Do If the Face detection App Stops Abnormally?<a name="EN-US_TOPIC_0196221486"></a>

## Symptom<a name="section1927414215210"></a>

When the  **bash stop\_facedetectionapp.sh 192.xxx.xxx.xxx**  command is run to stop the face detection app, the following error information is displayed:

```
 kill 192.xxx.xxx.xxx:ascend_facedetectionapp running failed, please login to kill it manually.
```

## Solution<a name="section191336320516"></a>

1.  Ensure that the entered IP address of the Atlas 200 DK developer board is correct.

    If the UI Host is connected in USB mode, the default IP address is  **192.168.1.2**. If the UI Host is connected in NIC mode, the default IP address is  **192.168.0.2**.

    -   If the IP address of the Atlas 200 DK developer board is correct, go to  [2](#li51548568817)  to manually stop the application processes.
    -   If the IP address of the Atals 200 DK developer board is incorrect, enter the correct IP address and run the  **bash stop\_facedetectionapp.sh 192.xxx.xxx.xxx**  command again.

2.  <a name="li51548568817"></a>Manually stop the face detection process on the Atlas 200 DK developer board.
    1.  Log in to the Atlas 200 DK developer board as the  **HwHiAiUser **user in SSH mode on the UI Host.
    2.  Run the following command to check the PID of the face detection app process:

        **ps -ef | grep face**

    3.  Run the following command to stop the face detection app process:

        **kill -9**  PID of the face detection app process



