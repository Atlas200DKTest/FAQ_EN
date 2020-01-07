# How Can I Implement SSH Password-free Login on the Atlas 200 DK?<a name="EN-US_TOPIC_0197154850"></a>

## Background<a name="section146509115335"></a>

The home directory of each user contains a hidden directory  **.ssh**, which stores the SSH configuration information.

## Procedure<a name="section85311431193814"></a>

1.  Run the following command on the Ubuntu host to generate a key file:

    If a key file exists in the  **.ssh **directory in the home directory of the user on the Ubuntu host, you do not need to run this command. Otherwise, the original key file is overwritten.

    **ssh-keygen**

    Perform configurations as prompted. After the command is executed, the SSH public key file  **id\_rsa.pub**  and private key file  **id\_rsa**  are automatically generated in the  **.ssh**  directory.

2.  Run the following command to save the public key file on the Ubuntu host to the Atlas 200 DK:

    **ssh-copy-id -p 22 HwHiAiUser@192.168.1.2**


