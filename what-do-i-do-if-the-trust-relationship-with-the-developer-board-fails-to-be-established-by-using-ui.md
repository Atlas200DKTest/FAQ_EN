# What Do I Do If the Trust Relationship with the Developer Board Fails to Be Established by Using UI Host?<a name="EN-US_TOPIC_0196221472"></a>

## Symptom<a name="en-us_topic_0179460235_section1834812122021"></a>

On the Ubuntu server where the UI Host is located, the following command is run to connect to the Atlas 200 DK developer board in SSH mode. A message is displayed, indicating that no trust relationship exists.

The following command is run on UI Host to re-establish the trust relationship:

**ssh-keygen -f "$HOME/.ssh/known\_hosts" -R  _192.168.1.2_**

**192.168.1.2**  is the IP address of the Atlas 200 DK developer board.

The following error is reported: 

```
ECDSA host key for 192.168.1.2 has changed and you have requested strict checking.
```

## Solution<a name="en-us_topic_0179460235_section23481824327"></a>

This error is caused by the invalid SSH information stored on the local host. Therefore, you need to clear the local SSH information and establish the connection again.

1.  On UI Host, clear the public key information about the connection to the 192.168.1.2 host of the current user.

    ssh-keygen -R  _192.168.1.2_

2.  Re-connect to the Atlas 200 DK developer board in SSH mode.

    ssh HwHiAiUser@192.168.1.2

    When the following information is displayed, enter  **yes**  to re-establish the SSH connection.

    ```
    The authenticity of host '192.168.1.2' can't be established.
    ECDSA key fingerprint is 53:b9:f9:30:67:ec:34:88:e8:bc:2a:a4:6f:3e:97:95.
    Are you sure you want to continue connecting (yes/no)? 
    ```


