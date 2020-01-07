# What Do I Do If the Error That IDE-daemon-client Not Found Is Reported When deploy.sh of Face Detection Is Running?<a name="EN-US_TOPIC_0197318582"></a>

## Description<a name="section135211697131"></a>

When the  **deploy.sh**  script of face detection is running, an error is reported, indicating that IDE-daemon-client tool is not found. However, this tool exists in the corresponding directory. After I switch to this directory, the IDE-daemon-client tool is available.

## Solution<a name="section16581739181519"></a>

This problem can be solved by using a soft link.

Run the following command in the  **/ddk/bin/x86\_64-linux-gcc5.4**  directory where the DDK is located to create a soft link:

ln -s /home/xxx/tools/che/ddk/ddk/bin/x86\_64-linux-gcc5.4/IDE-daemon-client /usr/lib/IDE-daemon-client

