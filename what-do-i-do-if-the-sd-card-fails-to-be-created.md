# What Do I Do If the SD Card Fails to Be Created?<a name="EN-US_TOPIC_0196221474"></a>

## Symptom<a name="en-us_topic_0177457284_sf93ddc90931d40a49ad498af15a811cd"></a>

If the SD card fails to be created, the  **make\_ubuntu\_sd.log**  file contains the following error information:

**extrack package, file name:/root/tools/log/squashfs-root/opt/mini/mini\_developerkit-XXXX.rar**

**extrack package\(/root/tools/log/squashfs-root/opt/mini/mini\_developerkit-XXX.rar\) fail, installation failed**

>![](public_sys-resources/icon-note.gif) **NOTE:**   
>The  **make\_ubuntu\_sd.log**  file is stored in  **$\{toolpath\}/bin**  on the Ubuntu server where  Mind Studio  is located.  
>**$\{toolpath\}**  is configured during  Mind Studio  installation. You can view the path in the  **$HOME/Mind-Studio/scripts/env.conf**  file.  

## Solution<a name="en-us_topic_0177457284_s361902cae8074163b01d4709b1260531"></a>

This error is caused by the lack of the  **unzip**  command on the Ubuntu server.

Switch to the  **root **user and run the  **apt-get install unzip**  command to resolve the problem.

